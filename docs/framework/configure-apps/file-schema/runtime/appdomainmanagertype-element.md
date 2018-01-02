---
title: '&lt;appDomainManagerType&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfdd9bcd1aa458aad705d4ab129646e746d63b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="7bb4d-102">&lt;appDomainManagerType&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="7bb4d-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="7bb4d-103">Especifica o tipo que serve como o gerenciador de domínio do aplicativo para o domínio do aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="7bb4d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7bb4d-104">\<configuration></span></span>  
<span data-ttu-id="7bb4d-105">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="7bb4d-105">\<runtime></span></span>  
<span data-ttu-id="7bb4d-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="7bb4d-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb4d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7bb4d-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bb4d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7bb4d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7bb4d-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bb4d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="7bb4d-110">Attributes</span></span>  
  
|<span data-ttu-id="7bb4d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="7bb4d-111">Attribute</span></span>|<span data-ttu-id="7bb4d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bb4d-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="7bb4d-113">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-113">Required attribute.</span></span> <span data-ttu-id="7bb4d-114">Especifica o nome do tipo, incluindo o namespace, que serve como o Gerenciador de domínio de aplicativo para o domínio de aplicativo padrão no processo.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bb4d-115">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7bb4d-115">Child Elements</span></span>  
 <span data-ttu-id="7bb4d-116">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bb4d-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7bb4d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7bb4d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7bb4d-118">Element</span></span>|<span data-ttu-id="7bb4d-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bb4d-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7bb4d-120">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7bb4d-121">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bb4d-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="7bb4d-122">Remarks</span></span>  
 <span data-ttu-id="7bb4d-123">Para especificar o tipo de Gerenciador de domínio de aplicativo, você deve especificar ambos os esse elemento e o [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="7bb4d-124">Se qualquer um desses elementos não for especificado, a outra será ignorada.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="7bb4d-125">Quando o domínio de aplicativo padrão é carregado, <xref:System.TypeLoadException> é gerada se o tipo especificado não existe no assembly que é especificado pelo [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento; e o processo falhará para Inicie.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="7bb4d-126">Quando você especifica o tipo de Gerenciador de domínio de aplicativo para o domínio de aplicativo padrão, outros domínios de aplicativo criados do domínio de aplicativo padrão herdam o tipo de Gerenciador de domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="7bb4d-127">Use o <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> e <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propriedades para especificar um tipo de Gerenciador de domínio de aplicativo diferente para um novo domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="7bb4d-128">Especificar o tipo de Gerenciador de domínio de aplicativo requer que o aplicativo tenha confiança total.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="7bb4d-129">(Por exemplo, um aplicativo em execução na área de trabalho tem confiança total). Se o aplicativo não tem a confiança total, um <xref:System.TypeLoadException> é gerada.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="7bb4d-130">O formato do tipo e do namespace é o mesmo formato que é usado para o <xref:System.Type.FullName%2A?displayProperty=nameWithType> propriedade.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="7bb4d-131">Este elemento de configuração está disponível apenas no [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e posterior.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb4d-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7bb4d-132">Example</span></span>  
 <span data-ttu-id="7bb4d-133">O exemplo a seguir mostra como especificar que o Gerenciador de domínio de aplicativo para o domínio de aplicativo padrão de um processo é o `MyMgr` digite o `AdMgrExample` assembly.</span><span class="sxs-lookup"><span data-stu-id="7bb4d-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bb4d-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7bb4d-134">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7bb4d-135">\<appDomainManagerAssembly > elemento</span><span class="sxs-lookup"><span data-stu-id="7bb4d-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [<span data-ttu-id="7bb4d-136">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="7bb4d-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="7bb4d-137">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="7bb4d-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="7bb4d-138">Método SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="7bb4d-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)