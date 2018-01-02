---
title: "Modelo de conteúdo do WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52cb3a5391d6e24643b03a880d3695a11baceca3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="wpf-content-model"></a><span data-ttu-id="fb922-102">Modelo de conteúdo do WPF</span><span class="sxs-lookup"><span data-stu-id="fb922-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="fb922-103"> é uma plataforma de apresentação que fornece muitos controles e tipos de controle cujo objetivo principal é exibir diferentes tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fb922-103"> is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="fb922-104">Para determinar qual controle usar ou de qual controle derivar, você deve compreender os tipos de objetos que um controle específico pode exibir.</span><span class="sxs-lookup"><span data-stu-id="fb922-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="fb922-105">Este tópico resume o modelo de conteúdo para os controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e o tipos semelhantes a controle.</span><span class="sxs-lookup"><span data-stu-id="fb922-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="fb922-106">O modelo de conteúdo descreve qual conteúdo pode ser usado em um controle.</span><span class="sxs-lookup"><span data-stu-id="fb922-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="fb922-107">Este tópico também lista as propriedades de conteúdo para cada modelo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fb922-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="fb922-108">Uma propriedade de conteúdo é uma propriedade que é usada para armazenar o conteúdo do objeto.</span><span class="sxs-lookup"><span data-stu-id="fb922-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="fb922-109">Classes que Contêm Conteúdo Arbitrário</span><span class="sxs-lookup"><span data-stu-id="fb922-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="fb922-110">Alguns controles podem conter um objeto de qualquer tipo, como uma cadeia de caracteres, um <xref:System.DateTime> objeto, ou um <xref:System.Windows.UIElement> que é um contêiner para outros itens.</span><span class="sxs-lookup"><span data-stu-id="fb922-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="fb922-111">Por exemplo, um <xref:System.Windows.Controls.Button> pode conter uma imagem e texto; ou um <xref:System.Windows.Controls.CheckBox> pode conter o valor de <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb922-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="fb922-112"> tem quatro classes que podem conter conteúdo arbitrário.</span><span class="sxs-lookup"><span data-stu-id="fb922-112"> has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="fb922-113">A tabela a seguir lista as classes, que herdam de <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="fb922-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="fb922-114">Classes que contêm conteúdo arbitrário</span><span class="sxs-lookup"><span data-stu-id="fb922-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="fb922-115">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="fb922-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="fb922-116">Um único objeto arbitrário.</span><span class="sxs-lookup"><span data-stu-id="fb922-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="fb922-117">Um cabeçalho e um único item, que são objetos arbitrários.</span><span class="sxs-lookup"><span data-stu-id="fb922-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="fb922-118">Uma coleção de objetos arbitrários.</span><span class="sxs-lookup"><span data-stu-id="fb922-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="fb922-119">Um cabeçalho e uma coleção de itens, que são objetos arbitrários.</span><span class="sxs-lookup"><span data-stu-id="fb922-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="fb922-120">Os controles que herdam essas classes podem conter o mesmo tipo de conteúdo e tratar o conteúdo da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="fb922-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="fb922-121">A ilustração a seguir mostra um controle de cada modelo de conteúdo que contém uma imagem e texto.</span><span class="sxs-lookup"><span data-stu-id="fb922-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="fb922-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="fb922-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="fb922-123">Controles que contêm um único objeto arbitrário</span><span class="sxs-lookup"><span data-stu-id="fb922-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="fb922-124">O <xref:System.Windows.Controls.ContentControl> classe contém uma única parte do conteúdo arbitrário.</span><span class="sxs-lookup"><span data-stu-id="fb922-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="fb922-125">A propriedade de conteúdo é <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="fb922-126">Os seguintes controles herdam <xref:System.Windows.Controls.ContentControl> e usar o modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fb922-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="fb922-127">A ilustração a seguir mostra quatro botões cujo <xref:System.Windows.Controls.ContentControl.Content%2A> é definido como uma cadeia de caracteres, um <xref:System.DateTime> objeto, um <xref:System.Windows.Shapes.Rectangle>e um <xref:System.Windows.Controls.Panel> que contém um <xref:System.Windows.Shapes.Ellipse> e um <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fb922-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="fb922-128">![Quatro botões](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="fb922-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="fb922-129">Quatro botões que têm diferentes tipos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="fb922-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="fb922-130">Para obter um exemplo de como definir o <xref:System.Windows.Controls.ContentControl.Content%2A> propriedade, consulte <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="fb922-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="fb922-131">Controles que contêm um único objeto arbitrário e um cabeçalho</span><span class="sxs-lookup"><span data-stu-id="fb922-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="fb922-132">O <xref:System.Windows.Controls.HeaderedContentControl> classe herda de <xref:System.Windows.Controls.ContentControl> e exibe o conteúdo com um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="fb922-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="fb922-133">Ele herda a propriedade de conteúdo, <xref:System.Windows.Controls.ContentControl.Content%2A>, de <xref:System.Windows.Controls.ContentControl> e define o <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> propriedade que é do tipo <xref:System.Object>; portanto, pode ser um objeto arbitrário.</span><span class="sxs-lookup"><span data-stu-id="fb922-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="fb922-134">Os seguintes controles herdam <xref:System.Windows.Controls.HeaderedContentControl> e usar o modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fb922-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="fb922-135">A ilustração a seguir mostra duas <xref:System.Windows.Controls.TabItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="fb922-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="fb922-136">A primeira <xref:System.Windows.Controls.TabItem> tem <xref:System.Windows.UIElement> objetos como o <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="fb922-137">O <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> é definido como um <xref:System.Windows.Controls.StackPanel> que contém um <xref:System.Windows.Shapes.Ellipse> e um <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fb922-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="fb922-138">O <xref:System.Windows.Controls.ContentControl.Content%2A> é definido como um <xref:System.Windows.Controls.StackPanel> que contém um <xref:System.Windows.Controls.TextBlock> e um <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="fb922-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="fb922-139">A segunda <xref:System.Windows.Controls.TabItem> tem uma cadeia de caracteres no <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e um <xref:System.Windows.Controls.TextBlock> no <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="fb922-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="fb922-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="fb922-141">TabControl que usa diferentes tipos de propriedade de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="fb922-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="fb922-142">Para obter um exemplo de como criar <xref:System.Windows.Controls.TabItem> objetos, consulte <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="fb922-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="fb922-143">Controles que contêm uma coleção de objetos arbitrários</span><span class="sxs-lookup"><span data-stu-id="fb922-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="fb922-144">O <xref:System.Windows.Controls.ItemsControl> classe herda de <xref:System.Windows.Controls.Control> e pode conter vários itens, como cadeias de caracteres, objetos ou outros elementos.</span><span class="sxs-lookup"><span data-stu-id="fb922-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="fb922-145">Suas propriedades de conteúdo são <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="fb922-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>normalmente é usado para popular o <xref:System.Windows.Controls.ItemsControl> com um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="fb922-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="fb922-147">Se você não deseja usar uma coleção para preencher o <xref:System.Windows.Controls.ItemsControl>, você pode adicionar itens usando o <xref:System.Windows.Controls.ItemsControl.Items%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="fb922-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="fb922-148">Os seguintes controles herdam <xref:System.Windows.Controls.ItemsControl> e usar o modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fb922-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="fb922-149">A ilustração a seguir mostra um <xref:System.Windows.Controls.ListBox> que contém esses tipos de itens:</span><span class="sxs-lookup"><span data-stu-id="fb922-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="fb922-150">Uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fb922-150">A string.</span></span>  
  
-   <span data-ttu-id="fb922-151">Um objeto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="fb922-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="fb922-152">Um <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="fb922-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="fb922-153">Um <xref:System.Windows.Controls.Panel> que contém um <xref:System.Windows.Shapes.Ellipse> e um <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fb922-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="fb922-154">![Caixa de listagem com quatro tipos de conteúdo](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="fb922-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="fb922-155">ListBox que contém vários tipos de objetos</span><span class="sxs-lookup"><span data-stu-id="fb922-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="fb922-156">Controles que contêm uma coleção de objetos arbitrários e um cabeçalho</span><span class="sxs-lookup"><span data-stu-id="fb922-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="fb922-157">O <xref:System.Windows.Controls.HeaderedItemsControl> classe herda de <xref:System.Windows.Controls.ItemsControl> e pode conter vários itens, como cadeias de caracteres, objetos, ou outros elementos e um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="fb922-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="fb922-158">Ele herda o <xref:System.Windows.Controls.ItemsControl> conteúdo propriedades, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, e <xref:System.Windows.Controls.ItemsControl.Items%2A>, e define o <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propriedade que pode ser um objeto arbitrário.</span><span class="sxs-lookup"><span data-stu-id="fb922-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="fb922-159">Os seguintes controles herdam <xref:System.Windows.Controls.HeaderedItemsControl> e usar o modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fb922-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="fb922-160">Classes que contêm uma coleção de objetos de UIElement</span><span class="sxs-lookup"><span data-stu-id="fb922-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="fb922-161">O <xref:System.Windows.Controls.Panel> classe posiciona e organiza filho <xref:System.Windows.UIElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="fb922-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="fb922-162">A propriedade de conteúdo é <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="fb922-163">As seguintes classes herdam o <xref:System.Windows.Controls.Panel> classe e usar o modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fb922-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="fb922-164">Para obter mais informações, consulte [Visão geral dos painéis](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="fb922-165">Classes que afetam a aparência de um UIElement</span><span class="sxs-lookup"><span data-stu-id="fb922-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="fb922-166">O <xref:System.Windows.Controls.Decorator> classe se aplica efeitos visuais e ao redor de um único filho <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="fb922-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="fb922-167">A propriedade de conteúdo é <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="fb922-168">As seguintes classes herdam <xref:System.Windows.Controls.Decorator> e usar o modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fb922-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="fb922-169">A ilustração a seguir mostra um <xref:System.Windows.Controls.TextBox> que tem (é decorado com) um <xref:System.Windows.Controls.Border> ao redor dele.</span><span class="sxs-lookup"><span data-stu-id="fb922-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="fb922-170">![Caixa de texto com borda preta](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="fb922-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="fb922-171">TextBlock que tem uma borda</span><span class="sxs-lookup"><span data-stu-id="fb922-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="fb922-172">Classes que fornecem comentários visuais sobre um UIElement</span><span class="sxs-lookup"><span data-stu-id="fb922-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="fb922-173">O <xref:System.Windows.Documents.Adorner> classe fornece indicações visuais para um usuário.</span><span class="sxs-lookup"><span data-stu-id="fb922-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="fb922-174">Por exemplo, use um <xref:System.Windows.Documents.Adorner> para adicionar ganchos funcionais a elementos ou fornecer informações de estado sobre um controle.</span><span class="sxs-lookup"><span data-stu-id="fb922-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="fb922-175">O <xref:System.Windows.Documents.Adorner> classe fornece uma estrutura para que você pode criar seus próprios adorners.</span><span class="sxs-lookup"><span data-stu-id="fb922-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="fb922-176"> não fornece adornos implementados.</span><span class="sxs-lookup"><span data-stu-id="fb922-176"> does not provide any implemented adorners.</span></span> <span data-ttu-id="fb922-177">Para mais informações, consulte [Visão geral dos adornos](../../../../docs/framework/wpf/controls/adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="fb922-178">Classes que habilitam os usuários a inserir texto</span><span class="sxs-lookup"><span data-stu-id="fb922-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="fb922-179">O WPF fornece três principais controles que habilitam os usuários a inserir texto.</span><span class="sxs-lookup"><span data-stu-id="fb922-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="fb922-180">Cada controle exibe o texto de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="fb922-180">Each control displays the text differently.</span></span> <span data-ttu-id="fb922-181">A tabela a seguir lista esses três controles relacionados ao texto, seus recursos quando eles exibem texto e suas propriedades que contêm o texto do controle.</span><span class="sxs-lookup"><span data-stu-id="fb922-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="fb922-182">Controle</span><span class="sxs-lookup"><span data-stu-id="fb922-182">Control</span></span>|<span data-ttu-id="fb922-183">O texto é exibido como</span><span class="sxs-lookup"><span data-stu-id="fb922-183">Text is displayed as</span></span>|<span data-ttu-id="fb922-184">Propriedade de conteúdo</span><span class="sxs-lookup"><span data-stu-id="fb922-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="fb922-185">Texto sem formatação</span><span class="sxs-lookup"><span data-stu-id="fb922-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="fb922-186">Texto formatado</span><span class="sxs-lookup"><span data-stu-id="fb922-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="fb922-187">Texto oculto (os caracteres são mascarados)</span><span class="sxs-lookup"><span data-stu-id="fb922-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="fb922-188">Classes que exibem seu texto</span><span class="sxs-lookup"><span data-stu-id="fb922-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="fb922-189">Várias classes podem ser usadas para exibir texto simples ou formatado.</span><span class="sxs-lookup"><span data-stu-id="fb922-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="fb922-190">Você pode usar <xref:System.Windows.Controls.TextBlock> para exibir pequenas quantidades de texto.</span><span class="sxs-lookup"><span data-stu-id="fb922-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="fb922-191">Se você quiser exibir grandes quantidades de texto, use o <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, ou <xref:System.Windows.Controls.FlowDocumentScrollViewer> controles.</span><span class="sxs-lookup"><span data-stu-id="fb922-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="fb922-192">O <xref:System.Windows.Controls.TextBlock> tem duas propriedades de conteúdo: <xref:System.Windows.Controls.TextBlock.Text%2A> e <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb922-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="fb922-193">Quando você deseja exibir o texto que usa a formatação consistente, o <xref:System.Windows.Controls.TextBlock.Text%2A> propriedade geralmente é a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="fb922-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="fb922-194">Se você planeja usar uma formatação diferente em todo o texto, use o <xref:System.Windows.Controls.TextBlock.Inlines%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="fb922-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="fb922-195">O <xref:System.Windows.Controls.TextBlock.Inlines%2A> propriedade é uma coleção de <xref:System.Windows.Documents.Inline> objetos, que especifica como formatar texto.</span><span class="sxs-lookup"><span data-stu-id="fb922-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="fb922-196">A tabela a seguir lista a propriedade de conteúdo para <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span><span class="sxs-lookup"><span data-stu-id="fb922-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="fb922-197">Controle</span><span class="sxs-lookup"><span data-stu-id="fb922-197">Control</span></span>|<span data-ttu-id="fb922-198">Propriedade de conteúdo</span><span class="sxs-lookup"><span data-stu-id="fb922-198">Content property</span></span>|<span data-ttu-id="fb922-199">Tipo de propriedade de conteúdo</span><span class="sxs-lookup"><span data-stu-id="fb922-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="fb922-200">Documento</span><span class="sxs-lookup"><span data-stu-id="fb922-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="fb922-201">Documento</span><span class="sxs-lookup"><span data-stu-id="fb922-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="fb922-202">Documento</span><span class="sxs-lookup"><span data-stu-id="fb922-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="fb922-203">O <xref:System.Windows.Documents.FlowDocument> implementa o <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; portanto, todas as três classes podem levar um <xref:System.Windows.Documents.FlowDocument> como conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fb922-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="fb922-204">Classes que formatam seu texto</span><span class="sxs-lookup"><span data-stu-id="fb922-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="fb922-205"><xref:System.Windows.Documents.TextElement>e suas classes relacionadas permitem que você formate o texto.</span><span class="sxs-lookup"><span data-stu-id="fb922-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="fb922-206"><xref:System.Windows.Documents.TextElement>objetos contêm e formatar o texto em <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> objetos.</span><span class="sxs-lookup"><span data-stu-id="fb922-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="fb922-207">Os dois tipos principais de <xref:System.Windows.Documents.TextElement> são objetos <xref:System.Windows.Documents.Block> elementos e <xref:System.Windows.Documents.Inline> elementos.</span><span class="sxs-lookup"><span data-stu-id="fb922-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="fb922-208">Um <xref:System.Windows.Documents.Block> elemento representa um bloco de texto, como uma lista ou um parágrafo.</span><span class="sxs-lookup"><span data-stu-id="fb922-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="fb922-209">Um <xref:System.Windows.Documents.Inline> elemento representa uma parte do texto em um bloco.</span><span class="sxs-lookup"><span data-stu-id="fb922-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="fb922-210">Muitos <xref:System.Windows.Documents.Inline> classes especificam a formatação de texto ao qual elas são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="fb922-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="fb922-211">Cada <xref:System.Windows.Documents.TextElement> tem seu próprio modelo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fb922-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="fb922-212">Para obter mais informações, consulte [Visão geral do modelo de conteúdo TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb922-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb922-213">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fb922-213">See Also</span></span>  
 [<span data-ttu-id="fb922-214">Avançado</span><span class="sxs-lookup"><span data-stu-id="fb922-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)