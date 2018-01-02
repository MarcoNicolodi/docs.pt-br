---
title: Usando a linha para novos registros no controle DataGridView dos Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4633a70f6c3d010e6cc75236778cf2fd59c0e05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2c08b-102">Usando a linha para novos registros no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c08b-102">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2c08b-103">Quando você usa um <xref:System.Windows.Forms.DataGridView> para editar dados em seu aplicativo, você geralmente deve dar aos usuários a capacidade de adicionar novas linhas de dados para o repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="2c08b-103">When you use a <xref:System.Windows.Forms.DataGridView> for editing data in your application, you will often want to give your users the ability to add new rows of data to the data store.</span></span> <span data-ttu-id="2c08b-104">O <xref:System.Windows.Forms.DataGridView> controle oferece suporte a essa funcionalidade, fornecendo uma linha para novos registros, que é sempre exibido como a última linha.</span><span class="sxs-lookup"><span data-stu-id="2c08b-104">The <xref:System.Windows.Forms.DataGridView> control supports this functionality by providing a row for new records, which is always shown as the last row.</span></span> <span data-ttu-id="2c08b-105">Ela é marcada com um símbolo de asterisco (*) em seu cabeçalho de linha.</span><span class="sxs-lookup"><span data-stu-id="2c08b-105">It is marked with an asterisk (*) symbol in its row header.</span></span> <span data-ttu-id="2c08b-106">As seções a seguir tratam de algumas coisas que você deve considerar quando programar com a linha de novos registros habilitada.</span><span class="sxs-lookup"><span data-stu-id="2c08b-106">The following sections discuss some of the things you should consider when you program with the row for new records enabled.</span></span>  
  
## <a name="displaying-the-row-for-new-records"></a><span data-ttu-id="2c08b-107">Exibindo a linha de novos registros</span><span class="sxs-lookup"><span data-stu-id="2c08b-107">Displaying the Row for New Records</span></span>  
 <span data-ttu-id="2c08b-108">Use o <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propriedade para indicar se a linha para novos registros é exibida.</span><span class="sxs-lookup"><span data-stu-id="2c08b-108">Use the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property to indicate whether the row for new records is displayed.</span></span> <span data-ttu-id="2c08b-109">O valor padrão dessa propriedade é `true`.</span><span class="sxs-lookup"><span data-stu-id="2c08b-109">The default value of this property is `true`.</span></span>  
  
 <span data-ttu-id="2c08b-110">Para os dados associados caso, a linha para novos registros será mostrada se a <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propriedade do controle e o <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> propriedade da fonte de dados são ambos `true`.</span><span class="sxs-lookup"><span data-stu-id="2c08b-110">For the data bound case, the row for new records will be shown if the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property of the control and the <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> property of the data source are both `true`.</span></span> <span data-ttu-id="2c08b-111">Se uma delas for `false`, a linha não será exibida.</span><span class="sxs-lookup"><span data-stu-id="2c08b-111">If either is `false` then the row will not be shown.</span></span>  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a><span data-ttu-id="2c08b-112">Preenchendo a linha de novos registros com os dados padrão</span><span class="sxs-lookup"><span data-stu-id="2c08b-112">Populating the Row for New Records with Default Data</span></span>  
 <span data-ttu-id="2c08b-113">Quando o usuário seleciona a linha para novos registros da linha atual, o <xref:System.Windows.Forms.DataGridView> controlar gera o <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.</span><span class="sxs-lookup"><span data-stu-id="2c08b-113">When the user selects the row for new records as the current row, the <xref:System.Windows.Forms.DataGridView> control raises the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <span data-ttu-id="2c08b-114">Esse evento fornece acesso ao novo <xref:System.Windows.Forms.DataGridViewRow> e permite que você preencher a nova linha com os dados padrão.</span><span class="sxs-lookup"><span data-stu-id="2c08b-114">This event provides access to the new <xref:System.Windows.Forms.DataGridViewRow> and enables you to populate the new row with default data.</span></span> <span data-ttu-id="2c08b-115">Para obter mais informações, consulte [Como especificar valores padrão para novas linhas no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="2c08b-115">For more information, see [How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)</span></span>  
  
## <a name="the-rows-collection"></a><span data-ttu-id="2c08b-116">A coleção de linhas</span><span class="sxs-lookup"><span data-stu-id="2c08b-116">The Rows Collection</span></span>  
 <span data-ttu-id="2c08b-117">A linha para novos registros está contida no <xref:System.Windows.Forms.DataGridView> do controle <xref:System.Windows.Forms.DataGridView.Rows%2A> coleção mas tem um comportamento diferente em dois aspectos:</span><span class="sxs-lookup"><span data-stu-id="2c08b-117">The row for new records is contained in the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.Rows%2A> collection but behaves differently in two respects:</span></span>  
  
-   <span data-ttu-id="2c08b-118">Não é possível remover a linha para novos registros de <xref:System.Windows.Forms.DataGridView.Rows%2A> coleção programaticamente.</span><span class="sxs-lookup"><span data-stu-id="2c08b-118">The row for new records cannot be removed from the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection programmatically.</span></span> <span data-ttu-id="2c08b-119">Um <xref:System.InvalidOperationException> é gerada se isso for tentado.</span><span class="sxs-lookup"><span data-stu-id="2c08b-119">An <xref:System.InvalidOperationException> is thrown if this is attempted.</span></span> <span data-ttu-id="2c08b-120">O usuário também não pode excluir a linha de novos registros.</span><span class="sxs-lookup"><span data-stu-id="2c08b-120">The user also cannot delete the row for new records.</span></span> <span data-ttu-id="2c08b-121">O <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> método não remove essa linha do <xref:System.Windows.Forms.DataGridView.Rows%2A> coleção.</span><span class="sxs-lookup"><span data-stu-id="2c08b-121">The <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> method does not remove this row from the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
-   <span data-ttu-id="2c08b-122">Nenhuma linha pode ser adicionada após a linha de novos registros.</span><span class="sxs-lookup"><span data-stu-id="2c08b-122">No row can be added after the row for new records.</span></span> <span data-ttu-id="2c08b-123">Um <xref:System.InvalidOperationException> é gerado se isso for tentado.</span><span class="sxs-lookup"><span data-stu-id="2c08b-123">An <xref:System.InvalidOperationException> is raised if this is attempted.</span></span> <span data-ttu-id="2c08b-124">Como resultado, a linha para novos registros é sempre a última linha a <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="2c08b-124">As a result, the row for new records is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2c08b-125">Os métodos em <xref:System.Windows.Forms.DataGridViewRowCollection> que adicionam linhas —<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, e <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>— todos chamar métodos de inserção internamente quando a linha para novos registros está presente.</span><span class="sxs-lookup"><span data-stu-id="2c08b-125">The methods on <xref:System.Windows.Forms.DataGridViewRowCollection> that add rows—<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, and <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>—all call insertion methods internally when the row for new records is present.</span></span>  
  
## <a name="visual-customization-of-the-row-for-new-records"></a><span data-ttu-id="2c08b-126">Personalização visual da linha de novos registros</span><span class="sxs-lookup"><span data-stu-id="2c08b-126">Visual Customization of the Row for New Records</span></span>  
 <span data-ttu-id="2c08b-127">Quando a linha para novos registros é criada, ele se baseia a linha especificada pelo <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="2c08b-127">When the row for new records is created, it is based on the row specified by the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span> <span data-ttu-id="2c08b-128">Qualquer estilo de célula que não for especificado para essa linha será herdado de outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="2c08b-128">Any cell styles that are not specified for this row are inherited from other properties.</span></span> <span data-ttu-id="2c08b-129">Para obter mais informações sobre herança de estilo de célula, consulte [Estilos de célula no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="2c08b-129">For more information about cell style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="2c08b-130">Os valores iniciais exibidos por células na linha para novos registros são recuperados de cada célula <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="2c08b-130">The initial values displayed by cells in the row for new records are retrieved from each cell's <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> property.</span></span> <span data-ttu-id="2c08b-131">Para células de tipo <xref:System.Windows.Forms.DataGridViewImageCell>, essa propriedade retorna uma imagem de espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="2c08b-131">For cells of type <xref:System.Windows.Forms.DataGridViewImageCell>, this property returns a placeholder image.</span></span> <span data-ttu-id="2c08b-132">Caso contrário, essa propriedade retornará `null`.</span><span class="sxs-lookup"><span data-stu-id="2c08b-132">Otherwise, this property returns `null`.</span></span> <span data-ttu-id="2c08b-133">Você pode substituir essa propriedade para retornar um valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2c08b-133">You can override this property to return a custom value.</span></span> <span data-ttu-id="2c08b-134">No entanto, esses valores iniciais podem ser substituídos por um <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> manipulador de eventos quando o foco entra na linha para novos registros.</span><span class="sxs-lookup"><span data-stu-id="2c08b-134">However, these initial values can be replaced by a <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event handler when focus enters the row for new records.</span></span>  
  
 <span data-ttu-id="2c08b-135">Os ícones padrão do cabeçalho dessa linha, que são uma seta ou um asterisco, não são expostos publicamente.</span><span class="sxs-lookup"><span data-stu-id="2c08b-135">The standard icons for this row's header, which are an arrow or an asterisk, are not exposed publicly.</span></span> <span data-ttu-id="2c08b-136">Se você desejar personalizar os ícones, você precisará criar um personalizado <xref:System.Windows.Forms.DataGridViewRowHeaderCell> classe.</span><span class="sxs-lookup"><span data-stu-id="2c08b-136">If you want to customize the icons, you will need to create a custom <xref:System.Windows.Forms.DataGridViewRowHeaderCell> class.</span></span>  
  
 <span data-ttu-id="2c08b-137">Usam os ícones padrão a <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> propriedade o <xref:System.Windows.Forms.DataGridViewCellStyle> em uso pela célula do cabeçalho de linha.</span><span class="sxs-lookup"><span data-stu-id="2c08b-137">The standard icons use the <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> property of the <xref:System.Windows.Forms.DataGridViewCellStyle> in use by the row header cell.</span></span> <span data-ttu-id="2c08b-138">Os ícones padrão não serão renderizados se não houver espaço suficiente para exibi-los completamente.</span><span class="sxs-lookup"><span data-stu-id="2c08b-138">The standard icons are not rendered if there is not enough space to display them completely.</span></span>  
  
 <span data-ttu-id="2c08b-139">Se a célula do cabeçalho de linha tiver um valor de cadeia de caracteres definido e, se não houver espaço suficiente para o texto e o ícone, o ícone será descartado primeiro.</span><span class="sxs-lookup"><span data-stu-id="2c08b-139">If the row header cell has a string value set, and if there is not enough room for both the text and icon, the icon is dropped first.</span></span>  
  
## <a name="sorting"></a><span data-ttu-id="2c08b-140">Classificação</span><span class="sxs-lookup"><span data-stu-id="2c08b-140">Sorting</span></span>  
 <span data-ttu-id="2c08b-141">No modo não vinculado, os novos registros sempre serão adicionados ao final do <xref:System.Windows.Forms.DataGridView> mesmo se o usuário classificou o conteúdo a <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2c08b-141">In unbound mode, new records will always be added to the end of the <xref:System.Windows.Forms.DataGridView> even if the user has sorted the content of the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="2c08b-142">O usuário precisará aplicar a classificação novamente para classificar a linha na posição correta; Esse comportamento é semelhante do <xref:System.Windows.Forms.ListView> controle.</span><span class="sxs-lookup"><span data-stu-id="2c08b-142">The user will need to apply the sort again in order to sort the row to the correct position; this behavior is similar to that of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="2c08b-143">Em modos virtuais ou com associação de dados, o comportamento de inserção quando uma classificação for aplicada dependerá da implementação do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="2c08b-143">In data bound and virtual modes, the insertion behavior when a sort is applied will be dependent on the implementation of the data model.</span></span> <span data-ttu-id="2c08b-144">Para [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], a linha é classificada imediatamente na posição correta.</span><span class="sxs-lookup"><span data-stu-id="2c08b-144">For [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], the row is immediately sorted into the correct position.</span></span>  
  
## <a name="other-notes-on-the-row-for-new-records"></a><span data-ttu-id="2c08b-145">Outras observações sobre a linha de novos registros</span><span class="sxs-lookup"><span data-stu-id="2c08b-145">Other Notes on the Row for New Records</span></span>  
 <span data-ttu-id="2c08b-146">Não é possível definir o <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> propriedade desta linha para `false`.</span><span class="sxs-lookup"><span data-stu-id="2c08b-146">You cannot set the <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> property of this row to `false`.</span></span> <span data-ttu-id="2c08b-147">Um <xref:System.InvalidOperationException> é gerado se isso for tentado.</span><span class="sxs-lookup"><span data-stu-id="2c08b-147">An <xref:System.InvalidOperationException> is raised if this is attempted.</span></span>  
  
 <span data-ttu-id="2c08b-148">A linha de novos registros sempre é criada no estado desmarcado.</span><span class="sxs-lookup"><span data-stu-id="2c08b-148">The row for new records is always created in the unselected state.</span></span>  
  
## <a name="virtual-mode"></a><span data-ttu-id="2c08b-149">Modo virtual</span><span class="sxs-lookup"><span data-stu-id="2c08b-149">Virtual Mode</span></span>  
 <span data-ttu-id="2c08b-150">Se estiver implementando o modo virtual, você precisará monitorar quando uma linha de novos registros é necessária no modelo de dados e o momento para reverter a adição da linha.</span><span class="sxs-lookup"><span data-stu-id="2c08b-150">If you are implementing virtual mode, you will need to track when a row for new records is needed in the data model and when to roll back the addition of the row.</span></span> <span data-ttu-id="2c08b-151">A implementação exata dessa funcionalidade depende da implementação do modelo de dados e de sua semântica de transação, por exemplo, se o escopo de confirmação está no nível da célula ou da linha.</span><span class="sxs-lookup"><span data-stu-id="2c08b-151">The exact implementation of this functionality depends on the implementation of the data model and its transaction semantics, for example, whether commit scope is at the cell or row level.</span></span> <span data-ttu-id="2c08b-152">Para obter mais informações, consulte [Modo virtual no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="2c08b-152">For more information, see [Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c08b-153">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2c08b-153">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [<span data-ttu-id="2c08b-154">Entrada de Dados no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c08b-154">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="2c08b-155">Como especificar valores padrão para novas linhas no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c08b-155">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)