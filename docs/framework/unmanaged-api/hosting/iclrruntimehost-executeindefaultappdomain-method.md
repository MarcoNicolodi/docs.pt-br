---
title: Método ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dcddb5766894a30f1ccb2552a09abe7153c6eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434946"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>Método ICLRRuntimeHost::ExecuteInDefaultAppDomain
Chama o método especificado do tipo especificado no assembly gerenciado especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pwzAssemblyPath`  
 [in] O caminho para o <xref:System.Reflection.Assembly> que define o <xref:System.Type> cujo método é invocado.  
  
 `pwzTypeName`  
 [in] O nome do <xref:System.Type> que define o método a ser invocado.  
  
 `pwzMethodName`  
 [in] O nome do método a ser invocado.  
  
 `pwzArgument`  
 [in] O parâmetro de cadeia de caracteres para passar para o método.  
  
 `pReturnValue`  
 [out] O valor de inteiro retornado pelo método invocado.  
  
## <a name="return-value"></a>Valor de retorno  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` retornou com êxito.|  
|HOST_E_CLRNOTAVAILABLE|O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.|  
|HOST_E_TIMEOUT|A chamada foi atingido.|  
|HOST_E_NOT_OWNER|O chamador não possui o bloqueio.|  
|HOST_E_ABANDONED|Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Se um método retornará E_FAIL, a CRL não será mais utilizável dentro do processo. As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentários  
 O método invocado deve ter a seguinte assinatura:  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 onde `pwzMethodName` representa o nome do método invocado, e `pwzArgument` representa o valor de cadeia de caracteres passado como um parâmetro para esse método. Se o valor HRESULT é definido como S_OK, `pReturnValue` é definido como o valor inteiro retornado pelo método invocado. Caso contrário, `pReturnValue` não está definido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Interface ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
