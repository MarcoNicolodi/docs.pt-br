---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 6684dcc485ef1ee2c3e5501f2fbc43898e172958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747288"
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
Representa uma seção de configuração para definir uma lista de backup que enumera um conjunto de pontos de extremidade que você deseja que o serviço de roteamento para usar no caso do ponto de extremidade primário não pode ser alcançado. Se o primeiro ponto de extremidade na lista estiver inativo, o serviço de roteamento irá automaticamente failover para o próximo na lista.  Isso fornece uma maneira rápida de adicionar confiabilidade para seu aplicativo sem ter que ensinar seu aplicativo cliente como lidar com padrões complexos ou onde todos os serviços são implantados.  
  
 \<system.serviceModel>  
\<roteamento >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|name|Uma cadeia de caracteres que especifica o nome usado para identificar esta lista de ponto de extremidade.|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<roteamento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Uma lista de pontos de extremidade de backup.|  
  
## <a name="remarks"></a>Comentários  
 Esta seção contém uma coleção ordenada de pontos de extremidade que uma mensagem será transmitida no caso de uma exceção de comunicação ao enviar para o ponto de extremidade primário.  
  
 Se um envio para o ponto de extremidade primário é listado no `endpointName` atributo de [ \<Adicionar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) falhará com uma exceção de comunicação, o serviço de roteamento tentará enviar a mensagem para o primeiro ponto de extremidade na seção de configuração. Se isso também falhará com uma exceção de comunicações, o serviço de roteamento tentará enviar a mensagem para a próxima mensagem contida nesta seção até que a tentativa de envio seja bem-sucedida, retorna uma falha que não seja uma exceção de comunicação ou todos os pontos de extremidade do coleção têm retornou uma falha.  
  
 No exemplo a seguir, se um envio para o ponto de extremidade primário chamado "Destino" retorna uma exceção de comunicação, o serviço tentará enviar a mensagem para "alternateServiceQueue". Se essa tentativa também retorna uma exceção de comunicação, o serviço de roteamento tentará enviar a mensagem para o próximo ponto de extremidade na coleção.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
