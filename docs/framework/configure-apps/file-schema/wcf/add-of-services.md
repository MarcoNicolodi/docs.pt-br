---
title: "&lt;adicionar&gt; &lt;serviços&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a859676adf48fda05040633fb8909d161e9ce8e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="99c3b-102">&lt;adicionar&gt; &lt;serviços&gt;</span><span class="sxs-lookup"><span data-stu-id="99c3b-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="99c3b-103">Especifica configurações para uma instância de <xref:System.Workflow.Runtime.WorkflowRuntime> para a hospedagem com base em fluxo de trabalho [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] serviços.</span><span class="sxs-lookup"><span data-stu-id="99c3b-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="99c3b-104">Esse elemento é do tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="99c3b-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="99c3b-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="99c3b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="99c3b-106">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="99c3b-106">\<behaviors></span></span>  
<span data-ttu-id="99c3b-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="99c3b-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="99c3b-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="99c3b-108">\<behavior></span></span>  
<span data-ttu-id="99c3b-109">\<Serviços ></span><span class="sxs-lookup"><span data-stu-id="99c3b-109">\<services></span></span>  
<span data-ttu-id="99c3b-110">\<add></span><span class="sxs-lookup"><span data-stu-id="99c3b-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c3b-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="99c3b-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c3b-112">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="99c3b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="99c3b-113">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="99c3b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c3b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="99c3b-114">Attributes</span></span>  
  
|<span data-ttu-id="99c3b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="99c3b-115">Attribute</span></span>|<span data-ttu-id="99c3b-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="99c3b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99c3b-117">tipo</span><span class="sxs-lookup"><span data-stu-id="99c3b-117">type</span></span>|<span data-ttu-id="99c3b-118">Uma cadeia de caracteres que especifica o nome de tipo qualificado por assembly do serviço a ser inicializado.</span><span class="sxs-lookup"><span data-stu-id="99c3b-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="99c3b-119">O serviço especificado deve seguir determinadas regras sobre as assinaturas dos seus construtores.</span><span class="sxs-lookup"><span data-stu-id="99c3b-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="99c3b-120">Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="99c3b-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c3b-121">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="99c3b-121">Child Elements</span></span>  
 <span data-ttu-id="99c3b-122">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="99c3b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99c3b-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="99c3b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="99c3b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="99c3b-124">Element</span></span>|<span data-ttu-id="99c3b-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="99c3b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99c3b-126">\<Serviços ></span><span class="sxs-lookup"><span data-stu-id="99c3b-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="99c3b-127">Uma coleção de serviços que serão adicionados para o <xref:System.Workflow.Runtime.WorkflowRuntime> mecanismo.</span><span class="sxs-lookup"><span data-stu-id="99c3b-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="99c3b-128">Os elementos são do tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="99c3b-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="99c3b-129">Os serviços especificados na coleção serão inicializados pelo mecanismo de tempo de execução de fluxo de trabalho e adicionados para seus serviços quando apropriado <xref:System.Workflow.Runtime.WorkflowRuntime> construtor seja chamado.</span><span class="sxs-lookup"><span data-stu-id="99c3b-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="99c3b-130">Portanto, os serviços especificados na coleção devem seguir determinadas regras sobre as assinaturas dos seus construtores.</span><span class="sxs-lookup"><span data-stu-id="99c3b-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="99c3b-131">Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="99c3b-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c3b-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="99c3b-132">Remarks</span></span>  
 <span data-ttu-id="99c3b-133">O serviço especificado nesse elemento será inicializado pelo mecanismo de tempo de execução de fluxo de trabalho e adicionado para seus serviços quando apropriado <xref:System.Workflow.Runtime.WorkflowRuntime> construtor seja chamado.</span><span class="sxs-lookup"><span data-stu-id="99c3b-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="99c3b-134">Portanto, o serviço especificado deve seguir determinadas regras sobre as assinaturas dos seus construtores.</span><span class="sxs-lookup"><span data-stu-id="99c3b-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="99c3b-135">Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="99c3b-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c3b-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="99c3b-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99c3b-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="99c3b-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="99c3b-138">Arquivos de configuração do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="99c3b-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)