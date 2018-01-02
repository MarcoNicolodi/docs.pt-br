---
title: "Como usar o padrão de detalhes mestre com dados hierárquicos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="334d0-102">Como usar o padrão de detalhes mestre com dados hierárquicos</span><span class="sxs-lookup"><span data-stu-id="334d0-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="334d0-103">Este exemplo mostra como implementar o cenário de detalhes mestre.</span><span class="sxs-lookup"><span data-stu-id="334d0-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="334d0-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="334d0-104">Example</span></span>  
 <span data-ttu-id="334d0-105">Neste exemplo, `LeagueList` é uma coleção de `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="334d0-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="334d0-106">Cada `League` tem um `Name` e uma coleção de `Divisions` e cada `Division` tem um nome e uma coleção de `Teams`.</span><span class="sxs-lookup"><span data-stu-id="334d0-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="334d0-107">Cada `Team` tem um nome de equipe.</span><span class="sxs-lookup"><span data-stu-id="334d0-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="334d0-108">Segue uma captura de tela do exemplo.</span><span class="sxs-lookup"><span data-stu-id="334d0-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="334d0-109">O `Divisions` <xref:System.Windows.Controls.ListBox> automaticamente controla as seleções no `Leagues` <xref:System.Windows.Controls.ListBox> e exibir os dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="334d0-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="334d0-110">O `Teams` <xref:System.Windows.Controls.ListBox> controla as seleções nos outros dois <xref:System.Windows.Controls.ListBox> controles.</span><span class="sxs-lookup"><span data-stu-id="334d0-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 <span data-ttu-id="334d0-111">![Exemplo de detalhes mestre&#45](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span><span class="sxs-lookup"><span data-stu-id="334d0-111">![Master&#45;detail example](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span></span>  
  
 <span data-ttu-id="334d0-112">As duas coisas a se observar neste exemplo são:</span><span class="sxs-lookup"><span data-stu-id="334d0-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="334d0-113">Os três <xref:System.Windows.Controls.ListBox> controles vinculados à mesma fonte.</span><span class="sxs-lookup"><span data-stu-id="334d0-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="334d0-114">Definir o <xref:System.Windows.Data.Binding.Path%2A> propriedade da associação para especificar qual nível de dados que você deseja o <xref:System.Windows.Controls.ListBox> para exibir.</span><span class="sxs-lookup"><span data-stu-id="334d0-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="334d0-115">Você deve definir o <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propriedade `true` no <xref:System.Windows.Controls.ListBox> controles que a seleção que você está rastreando.</span><span class="sxs-lookup"><span data-stu-id="334d0-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="334d0-116">A definição dessa propriedade garante que o item selecionado é sempre definido como o <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="334d0-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="334d0-117">Como alternativa, se o <xref:System.Windows.Controls.ListBox> obtém seus dados de um <xref:System.Windows.Data.CollectionViewSource>, ele sincroniza automaticamente seleção e moeda.</span><span class="sxs-lookup"><span data-stu-id="334d0-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="334d0-118">A técnica é um pouco diferente quando você usa dados [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="334d0-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="334d0-119">Para ver um exemplo, confira [Usar o padrão de detalhes mestre com os dados XML hierárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="334d0-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334d0-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="334d0-120">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="334d0-121">Associar a uma coleção e exibir informações com base na seleção</span><span class="sxs-lookup"><span data-stu-id="334d0-121">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="334d0-122">Visão geral da vinculação de dados</span><span class="sxs-lookup"><span data-stu-id="334d0-122">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="334d0-123">Visão geral de modelagem dos dados</span><span class="sxs-lookup"><span data-stu-id="334d0-123">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="334d0-124">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="334d0-124">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)