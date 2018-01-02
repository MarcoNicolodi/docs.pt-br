---
title: '&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b6043b35ea9dbed1e1e6e170035436038334b34
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="74b6a-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="74b6a-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="74b6a-103">Especifica as configurações de uma credencial de serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="74b6a-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="74b6a-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="74b6a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="74b6a-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="74b6a-105">\<behaviors></span></span>  
<span data-ttu-id="74b6a-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="74b6a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="74b6a-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="74b6a-107">\<behavior></span></span>  
<span data-ttu-id="74b6a-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="74b6a-108">\<serviceCredentials></span></span>  
<span data-ttu-id="74b6a-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="74b6a-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b6a-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="74b6a-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74b6a-111">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="74b6a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="74b6a-112">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="74b6a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74b6a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="74b6a-113">Attributes</span></span>  
  
|<span data-ttu-id="74b6a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="74b6a-114">Attribute</span></span>|<span data-ttu-id="74b6a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="74b6a-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="74b6a-116">Um atributo booleano opcional que especifica se o sistema inclui grupos do Windows no contexto de segurança.</span><span class="sxs-lookup"><span data-stu-id="74b6a-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="74b6a-117">O padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="74b6a-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="74b6a-118">A configuração desse atributo `true` tem um impacto de desempenho que resulta em uma expansão de grupo completo.</span><span class="sxs-lookup"><span data-stu-id="74b6a-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="74b6a-119">Defina este atributo como `false` se você não precisa estabelecer a lista de grupos de um usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="74b6a-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="74b6a-120">Um atributo booleano opcional que especifica se chamadores anônimos, não autenticados são permitidos.</span><span class="sxs-lookup"><span data-stu-id="74b6a-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="74b6a-121">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="74b6a-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="74b6a-122">Quando o `clientCredentialType` atributo de uma associação é definido como `Windows`, o sistema não permite chamadores anônimos.</span><span class="sxs-lookup"><span data-stu-id="74b6a-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="74b6a-123">Isso significa que somente domínio ou grupo de trabalho autenticado chamadores têm permissão para acessar o sistema.</span><span class="sxs-lookup"><span data-stu-id="74b6a-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="74b6a-124">Você pode substituir esse comportamento usando esse atributo.</span><span class="sxs-lookup"><span data-stu-id="74b6a-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="74b6a-125">Use essa configuração com extrema cautela.</span><span class="sxs-lookup"><span data-stu-id="74b6a-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74b6a-126">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="74b6a-126">Child Elements</span></span>  
 <span data-ttu-id="74b6a-127">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="74b6a-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74b6a-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="74b6a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="74b6a-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="74b6a-129">Element</span></span>|<span data-ttu-id="74b6a-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="74b6a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74b6a-131">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="74b6a-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="74b6a-132">Especifica a credencial a ser usado na autenticação do serviço e as configurações de relacionadas à validação de credenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="74b6a-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74b6a-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="74b6a-133">Remarks</span></span>  
 <span data-ttu-id="74b6a-134">Use esse elemento para especificar se deseja permitir acesso de usuários anônimos do Windows, definindo o `allowAnonymousLogons` atributo.</span><span class="sxs-lookup"><span data-stu-id="74b6a-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="74b6a-135">Você também pode especificar se deseja incluir informações de grupo ao qual pertencem os usuários no AuthorizationContext, definindo o `includeWindowsGroups` atributo.</span><span class="sxs-lookup"><span data-stu-id="74b6a-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="74b6a-136">Se for definido como `true` (a configuração padrão), o serviço pode determinar os grupos do Windows ao qual o cliente pertence.</span><span class="sxs-lookup"><span data-stu-id="74b6a-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b6a-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="74b6a-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>