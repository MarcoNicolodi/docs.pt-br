---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4f05b8164c0920893ea5b379017b1eb91f1b37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="a4515-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="a4515-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="a4515-103">Um elemento de configuração que permite adicionar configurações que definem as configurações de ativação de serviços virtuais que são mapeados para seus [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tipos de serviço.</span><span class="sxs-lookup"><span data-stu-id="a4515-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="a4515-104">Isso torna possível para ativar serviços hospedados no WAS / IIS sem um arquivo. svc.</span><span class="sxs-lookup"><span data-stu-id="a4515-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="a4515-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a4515-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4515-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="a4515-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="a4515-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="a4515-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4515-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4515-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4515-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a4515-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a4515-110">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="a4515-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4515-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4515-111">Attributes</span></span>  
 <span data-ttu-id="a4515-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a4515-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4515-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a4515-113">Child Elements</span></span>  
  
|<span data-ttu-id="a4515-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4515-114">Element</span></span>|<span data-ttu-id="a4515-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4515-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4515-116">\<add></span><span class="sxs-lookup"><span data-stu-id="a4515-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="a4515-117">Adiciona um elemento de configuração que especifica a ativação de um aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="a4515-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4515-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a4515-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a4515-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4515-119">Element</span></span>|<span data-ttu-id="a4515-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4515-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4515-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="a4515-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="a4515-122">Define o tipo que o ambiente de hospedagem de serviço instancia para um transporte particular.</span><span class="sxs-lookup"><span data-stu-id="a4515-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4515-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="a4515-123">Remarks</span></span>  
 <span data-ttu-id="a4515-124">O exemplo a seguir mostra como definir as configurações de ativação em seu arquivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="a4515-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a4515-125">Usando esta configuração, você pode ativar o GreetingService sem usar um arquivo. svc.</span><span class="sxs-lookup"><span data-stu-id="a4515-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="a4515-126">Observe que `<serviceHostingEnvironment>` é uma configuração de nível de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a4515-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="a4515-127">Você precisa colocar a `web.config` que contém a configuração abaixo da raiz do aplicativo virtual.</span><span class="sxs-lookup"><span data-stu-id="a4515-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="a4515-128">Além disso, `serviceHostingEnvironment` uma seção herdáveis machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="a4515-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="a4515-129">Se você registrar um único serviço na raiz da máquina, cada serviço no aplicativo herdará esse serviço.</span><span class="sxs-lookup"><span data-stu-id="a4515-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="a4515-130">Ativação baseada em configuração oferece suporte à ativação pelo protocolo http e não http.</span><span class="sxs-lookup"><span data-stu-id="a4515-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="a4515-131">Ele requer extensões no relatativeAddress ou seja,. svc,. xoml ou .xamlx.</span><span class="sxs-lookup"><span data-stu-id="a4515-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="a4515-132">Você pode mapear suas próprias extensões para o buildProviders sabe, que, em seguida, permite que você ative o serviço em qualquer extensão.</span><span class="sxs-lookup"><span data-stu-id="a4515-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="a4515-133">Em conflito, a `<serviceActivations>` seção substitui registros. svc.</span><span class="sxs-lookup"><span data-stu-id="a4515-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4515-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a4515-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>