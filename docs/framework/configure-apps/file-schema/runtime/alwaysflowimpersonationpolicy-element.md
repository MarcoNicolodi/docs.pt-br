---
title: '&lt;alwaysFlowImpersonationPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be1df955f7586848968cb32cd66a4c6889cfffa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="df242-102">&lt;alwaysFlowImpersonationPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="df242-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="df242-103">Especifica que a identidade do Windows sempre fluirá por pontos assíncronos, independentemente de como a representação tenha sido executada.</span><span class="sxs-lookup"><span data-stu-id="df242-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="df242-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="df242-104">\<configuration></span></span>  
<span data-ttu-id="df242-105">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="df242-105">\<runtime></span></span>  
<span data-ttu-id="df242-106">\<alwaysFlowImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="df242-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df242-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df242-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df242-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="df242-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df242-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="df242-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df242-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="df242-110">Attributes</span></span>  
  
|<span data-ttu-id="df242-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="df242-111">Attribute</span></span>|<span data-ttu-id="df242-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="df242-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="df242-113">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="df242-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="df242-114">Indica se a identidade do Windows flui pelos pontos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="df242-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="df242-115">Atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="df242-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="df242-116">Valor</span><span class="sxs-lookup"><span data-stu-id="df242-116">Value</span></span>|<span data-ttu-id="df242-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="df242-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="df242-118">O identity não fluem pelos pontos assíncronos, a menos que a representação é realizada por meio do Windows gerenciado métodos como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="df242-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="df242-119">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="df242-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="df242-120">A identidade do Windows sempre flui pelos pontos assíncronos, independentemente de como a representação foi executada.</span><span class="sxs-lookup"><span data-stu-id="df242-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df242-121">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="df242-121">Child Elements</span></span>  
 <span data-ttu-id="df242-122">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="df242-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df242-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="df242-123">Parent Elements</span></span>  
  
|<span data-ttu-id="df242-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="df242-124">Element</span></span>|<span data-ttu-id="df242-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="df242-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="df242-126">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df242-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="df242-127">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="df242-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df242-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="df242-128">Remarks</span></span>  
 <span data-ttu-id="df242-129">Nas versões do .NET Framework 1.0 e 1.1, a identidade do Windows não fluem pelos pontos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="df242-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="df242-130">No .NET Framework versão 2.0, há um <xref:System.Threading.ExecutionContext> objeto que contém informações sobre o thread em execução no momento e ele ultrapassar assíncronos pontos em um domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="df242-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="df242-131">O <xref:System.Security.Principal.WindowsIdentity> também fluxos como parte das informações que fluem pelos pontos assíncronos, desde que a representação foi obtida usando gerenciado métodos como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e não por outros meios, como plataforma invocar métodos nativos.</span><span class="sxs-lookup"><span data-stu-id="df242-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="df242-132">Esse elemento é usado para especificar que a identidade do Windows fluxo pelos pontos assíncronos, independentemente de como a representação foi alcançada.</span><span class="sxs-lookup"><span data-stu-id="df242-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="df242-133">Você pode alterar esse comportamento padrão de duas outras maneiras:</span><span class="sxs-lookup"><span data-stu-id="df242-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="df242-134">No código gerenciado em uma base por thread.</span><span class="sxs-lookup"><span data-stu-id="df242-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="df242-135">Você pode suprimir o fluxo em uma base por thread, modificando o <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> configurações usando o <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, ou <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="df242-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="df242-136">Na chamada para a interface de hospedagem não gerenciada para carregar o common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="df242-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="df242-137">Se uma interface de hospedagem não gerenciada (em vez de um executável gerenciado simple) é usada para carregar o CLR, você pode especificar um sinalizador especial na chamada para o [função CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) função.</span><span class="sxs-lookup"><span data-stu-id="df242-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="df242-138">Para habilitar o modo de compatibilidade para todo o processo, defina o `flags` parâmetro [função CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) para `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="df242-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="df242-139">Arquivo de Configuração</span><span class="sxs-lookup"><span data-stu-id="df242-139">Configuration File</span></span>  
 <span data-ttu-id="df242-140">Em um aplicativo do .NET Framework, esse elemento pode ser usado apenas no arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="df242-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="df242-141">Para um aplicativo ASP.NET, o fluxo de representação pode ser configurado no arquivo ASPNET encontrado na \<pasta Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.</span><span class="sxs-lookup"><span data-stu-id="df242-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="df242-142">ASP.NET por padrão desabilita o fluxo de representação no arquivo ASPNET usando as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="df242-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="df242-143">No ASP.NET, se quiser permitir que o fluxo de representação em vez disso, você deve usar explicitamente as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="df242-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="df242-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="df242-144">Example</span></span>  
 <span data-ttu-id="df242-145">O exemplo a seguir mostra como especificar a identidade do Windows flui pelos pontos assíncronos, mesmo quando a representação é obtida através de meios diferentes métodos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="df242-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="df242-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="df242-146">See Also</span></span>  
 [<span data-ttu-id="df242-147">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="df242-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="df242-148">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="df242-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="df242-149">\<legacyImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="df242-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)