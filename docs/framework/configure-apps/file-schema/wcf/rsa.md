---
title: '&lt;RSA&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 714036b6f7cb64fd12cd48eabb4203279431e5a6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltrsagt"></a><span data-ttu-id="eb3a1-102">&lt;RSA&gt;</span><span class="sxs-lookup"><span data-stu-id="eb3a1-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="eb3a1-103">Um cliente WCF seguro que se conecta a um ponto de extremidade com esta identidade verifica que as declarações apresentadas pelo servidor contém uma declaração que contém a chave pública RSA usada para construir essa identidade.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="eb3a1-104">\<identidade ></span><span class="sxs-lookup"><span data-stu-id="eb3a1-104">\<identity></span></span>  
<span data-ttu-id="eb3a1-105">\<RSA ></span><span class="sxs-lookup"><span data-stu-id="eb3a1-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3a1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eb3a1-106">Syntax</span></span>  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb3a1-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="eb3a1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="eb3a1-108">As seções a seguir descrevem os elementos pai de atributos e elementos filho</span><span class="sxs-lookup"><span data-stu-id="eb3a1-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb3a1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="eb3a1-109">Attributes</span></span>  
  
|<span data-ttu-id="eb3a1-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="eb3a1-110">Attribute</span></span>|<span data-ttu-id="eb3a1-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb3a1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb3a1-112">Valor </span><span class="sxs-lookup"><span data-stu-id="eb3a1-112">value</span></span>|<span data-ttu-id="eb3a1-113">Cadeia de caracteres opcional.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-113">Optional String.</span></span> <span data-ttu-id="eb3a1-114">O RSA valor da chave pública a ser comparado com o cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb3a1-115">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="eb3a1-115">Child Elements</span></span>  
 <span data-ttu-id="eb3a1-116">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eb3a1-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb3a1-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="eb3a1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="eb3a1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb3a1-118">Element</span></span>|<span data-ttu-id="eb3a1-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb3a1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb3a1-120">\<identidade ></span><span class="sxs-lookup"><span data-stu-id="eb3a1-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="eb3a1-121">Especifica a identidade do serviço para ser autenticado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb3a1-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="eb3a1-122">Remarks</span></span>  
 <span data-ttu-id="eb3a1-123">Uma verificação RSA permite restringir especificamente a autenticação para um único certificado com base em sua chave RSA ou gerado seu próprio valor de chave RSA.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="eb3a1-124">Este permite mais rígida a autenticação de uma chave RSA específica às custas de serviço não trabalhar com os clientes existentes se o valor da chave RSA é alterado.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="eb3a1-125">Para obter mais informações sobre como usar a identidade para validar um serviço para um cliente, consulte [autenticação e identidade de serviço](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="eb3a1-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb3a1-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eb3a1-126">Example</span></span>  
 <span data-ttu-id="eb3a1-127">O código de configuração a seguir especifica o valor da chave pública de um certificado x. 509 que é usado para autenticar um servidor.</span><span class="sxs-lookup"><span data-stu-id="eb3a1-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb3a1-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eb3a1-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [<span data-ttu-id="eb3a1-129">Autenticação e identidade de serviço</span><span class="sxs-lookup"><span data-stu-id="eb3a1-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="eb3a1-130">\<identidade ></span><span class="sxs-lookup"><span data-stu-id="eb3a1-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)