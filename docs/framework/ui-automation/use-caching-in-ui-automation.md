---
title: "Usar armazenamento em cache em automação de interface do usuário"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 9576389c7245810eeef3c86926e479dedfdfbb69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="2b9d3-102">Usar armazenamento em cache em automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2b9d3-102">Use Caching in UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="2b9d3-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2b9d3-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="2b9d3-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="2b9d3-105">Esta seção mostra como implementar cache de <xref:System.Windows.Automation.AutomationElement> propriedades e padrões de controle.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-105">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="2b9d3-106">Ativar uma solicitação de Cache</span><span class="sxs-lookup"><span data-stu-id="2b9d3-106">Activate a Cache Request</span></span>  
  
1.  <span data-ttu-id="2b9d3-107">Criará um <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-107">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="2b9d3-108">Especificar as propriedades e padrões de cache usando <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-108">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3.  <span data-ttu-id="2b9d3-109">Especifique o escopo de armazenamento em cache, definindo o <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-109">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4.  <span data-ttu-id="2b9d3-110">Especifique o modo de exibição da subárvore definindo o <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-110">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5.  <span data-ttu-id="2b9d3-111">Definir o <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> propriedade <xref:System.Windows.Automation.AutomationElementMode.None> se você quiser aumentar a eficiência não recuperando uma referência completa a objetos.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-111">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="2b9d3-112">(Isso tornará impossível recuperar valores atuais desses objetos.)</span><span class="sxs-lookup"><span data-stu-id="2b9d3-112">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6.  <span data-ttu-id="2b9d3-113">Ativar a solicitação usando <xref:System.Windows.Automation.CacheRequest.Activate%2A> dentro de um `using` bloco (`Using` em [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="2b9d3-113">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>  
  
 <span data-ttu-id="2b9d3-114">Depois de obter <xref:System.Windows.Automation.AutomationElement> objetos ou inscrever-se em eventos, desative a solicitação usando <xref:System.Windows.Automation.CacheRequest.Pop%2A> (se <xref:System.Windows.Automation.CacheRequest.Push%2A> foi usado) ou removendo o objeto criado pelo <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-114">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="2b9d3-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> em uma `using` bloco (`Using` em [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="2b9d3-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="2b9d3-116">Propriedades do cache AutomationElement</span><span class="sxs-lookup"><span data-stu-id="2b9d3-116">Cache AutomationElement Properties</span></span>  
  
1.  <span data-ttu-id="2b9d3-117">Enquanto um <xref:System.Windows.Automation.CacheRequest> está ativa, obter <xref:System.Windows.Automation.AutomationElement> objetos usando <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> ou <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; ou obtenha um <xref:System.Windows.Automation.AutomationElement> como a origem de um evento que você registrou para quando o <xref:System.Windows.Automation.CacheRequest> estava ativo.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-117">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="2b9d3-118">(Você também pode criar um cache, passando um <xref:System.Windows.Automation.CacheRequest> GetUpdatedCache ou uma da <xref:System.Windows.Automation.TreeWalker> métodos.)</span><span class="sxs-lookup"><span data-stu-id="2b9d3-118">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="2b9d3-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> ou recuperar uma propriedade do <xref:System.Windows.Automation.AutomationElement.Cached%2A> propriedade o <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="2b9d3-120">Obter padrões em cache e suas propriedades</span><span class="sxs-lookup"><span data-stu-id="2b9d3-120">Obtain Cached Patterns and Their Properties</span></span>  
  
1.  <span data-ttu-id="2b9d3-121">Enquanto um <xref:System.Windows.Automation.CacheRequest> está ativa, obter <xref:System.Windows.Automation.AutomationElement> objetos usando <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> ou <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; ou obtenha um <xref:System.Windows.Automation.AutomationElement> como a origem de um evento que você registrou para quando o <xref:System.Windows.Automation.CacheRequest> estava ativo.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-121">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="2b9d3-122">(Você também pode criar um cache, passando um <xref:System.Windows.Automation.CacheRequest> GetUpdatedCache ou uma da <xref:System.Windows.Automation.TreeWalker> métodos.)</span><span class="sxs-lookup"><span data-stu-id="2b9d3-122">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="2b9d3-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> ou <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> para recuperar um padrão em cache.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3.  <span data-ttu-id="2b9d3-124">Recuperar valores de propriedade do `Cached` propriedade do padrão de controle.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-124">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b9d3-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2b9d3-125">Example</span></span>  
 <span data-ttu-id="2b9d3-126">O exemplo de código a seguir mostra vários aspectos do armazenamento em cache, o uso de <xref:System.Windows.Automation.CacheRequest.Activate%2A> para ativar o <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-126">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="2b9d3-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2b9d3-127">Example</span></span>  
 <span data-ttu-id="2b9d3-128">O exemplo de código a seguir mostra vários aspectos do armazenamento em cache, o uso de <xref:System.Windows.Automation.CacheRequest.Push%2A> para ativar o <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="2b9d3-129">Exceto quando você deseja aninhar solicitações de cache, é preferível usar <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b9d3-129">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="2b9d3-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2b9d3-130">See Also</span></span>  
 [<span data-ttu-id="2b9d3-131">Armazenamento em cache em clientes de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2b9d3-131">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)