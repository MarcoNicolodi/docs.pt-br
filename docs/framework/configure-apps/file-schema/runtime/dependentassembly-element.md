---
title: '&lt;dependentAssembly&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a968d2d1abf6e77cddd9d0a0367822ee4f9723ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdependentassemblygt-element"></a><span data-ttu-id="25143-102">&lt;dependentAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="25143-102">&lt;dependentAssembly&gt; Element</span></span>
<span data-ttu-id="25143-103">Encapsula local do assembly e política de associação para cada assembly.</span><span class="sxs-lookup"><span data-stu-id="25143-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="25143-104">Use um `dependentAssembly` elemento para cada assembly.</span><span class="sxs-lookup"><span data-stu-id="25143-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="25143-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="25143-105">\<configuration></span></span>  
<span data-ttu-id="25143-106">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="25143-106">\<runtime></span></span>  
<span data-ttu-id="25143-107">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="25143-107">\<assemblyBinding></span></span>  
<span data-ttu-id="25143-108">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="25143-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25143-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25143-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25143-110">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="25143-110">Attributes and Elements</span></span>  
 <span data-ttu-id="25143-111">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="25143-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25143-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="25143-112">Attributes</span></span>  
 <span data-ttu-id="25143-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="25143-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25143-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="25143-114">Child Elements</span></span>  
  
|<span data-ttu-id="25143-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="25143-115">Element</span></span>|<span data-ttu-id="25143-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="25143-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="25143-117">Contém informações de identificação sobre o assembly.</span><span class="sxs-lookup"><span data-stu-id="25143-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="25143-118">Esse elemento deve ser incluído em cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="25143-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="25143-119">Especifica onde o tempo de execução pode encontrar um assembly compartilhado se ele não estiver instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="25143-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="25143-120">Redireciona uma versão do assembly para outra.</span><span class="sxs-lookup"><span data-stu-id="25143-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="25143-121">Especifica se o tempo de execução se aplica a política de editor para esse assembly.</span><span class="sxs-lookup"><span data-stu-id="25143-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25143-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="25143-122">Parent Elements</span></span>  
  
|<span data-ttu-id="25143-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="25143-123">Element</span></span>|<span data-ttu-id="25143-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="25143-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="25143-125">Contém informações sobre o redirecionamento de versão e os locais dos assemblies.</span><span class="sxs-lookup"><span data-stu-id="25143-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="25143-126">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="25143-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="25143-127">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="25143-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="25143-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25143-128">Example</span></span>  
 <span data-ttu-id="25143-129">O exemplo a seguir mostra como encapsular as informações de assembly para dois assemblies.</span><span class="sxs-lookup"><span data-stu-id="25143-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="25143-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="25143-130">See Also</span></span>  
 [<span data-ttu-id="25143-131">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="25143-131">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="25143-132">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="25143-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="25143-133">Redirecionando versões de assembly</span><span class="sxs-lookup"><span data-stu-id="25143-133">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)