---
title: "Instruções passo a passo: criando um controle não associado DataGridView dos Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2c57cfbab4d3af6cebff96517383999ae5b73d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="7ebc1-102">Instruções passo a passo: criando um controle não associado DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ebc1-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7ebc1-103">Você pode querer exibir com frequência dados tabulares que não se originam de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="7ebc1-104">Por exemplo, você talvez queira mostrar o conteúdo de uma matriz bidimensional de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="7ebc1-105">O <xref:System.Windows.Forms.DataGridView> classe fornece uma maneira fácil e altamente personalizável para exibir dados sem associação a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="7ebc1-106">Este passo a passo mostra como preencher um <xref:System.Windows.Forms.DataGridView> controlar e gerenciar a adição e exclusão de linhas no modo "não acoplado".</span><span class="sxs-lookup"><span data-stu-id="7ebc1-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="7ebc1-107">Por padrão, o usuário pode adicionar novas linhas.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-107">By default, the user can add new rows.</span></span> <span data-ttu-id="7ebc1-108">Para evitar a adição de linha, defina a <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> é de propriedade `false`.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="7ebc1-109">Para copiar o código deste tópico como uma única lista, consulte [Como criar um controle DataGridView não associado do Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7ebc1-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="7ebc1-110">Criando o formulário</span><span class="sxs-lookup"><span data-stu-id="7ebc1-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="7ebc1-111">Para usar um controle DataGridView não associado</span><span class="sxs-lookup"><span data-stu-id="7ebc1-111">To use an unbound DataGridView control</span></span>  
  
1.  <span data-ttu-id="7ebc1-112">Criar uma classe que deriva de <xref:System.Windows.Forms.Form> e contém as seguintes declarações variáveis e `Main` método.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  <span data-ttu-id="7ebc1-113">Implemente um método `SetupLayout` na definição de classe do formulário para configurar o layout do formulário.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  <span data-ttu-id="7ebc1-114">Criar um `SetupDataGridView` método para configurar o <xref:System.Windows.Forms.DataGridView> colunas e propriedades.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="7ebc1-115">Este método adiciona primeiro o <xref:System.Windows.Forms.DataGridView> controle para o formulário <xref:System.Windows.Forms.Control.Controls%2A> coleção.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="7ebc1-116">Em seguida, o número de colunas a serem exibidas é definido usando o <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="7ebc1-117">O estilo dos cabeçalhos de coluna é definido, definindo o <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, e <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> propriedades do <xref:System.Windows.Forms.DataGridViewCellStyle> retornado pelo <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="7ebc1-118">Propriedades de aparência e layout são definidas e, em seguida, os nomes de coluna são atribuídos.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="7ebc1-119">Quando esse método for encerrada, o <xref:System.Windows.Forms.DataGridView> controle está pronto para ser preenchido.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  <span data-ttu-id="7ebc1-120">Criar um `PopulateDataGridView` método para adicionar linhas para o <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="7ebc1-121">Cada linha representa uma música e suas informações associadas.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  <span data-ttu-id="7ebc1-122">Com os métodos de utilitário em vigor, você pode anexar manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="7ebc1-123">Manipulará o **adicionar** e **excluir** dos botões <xref:System.Windows.Forms.Control.Click> eventos, o formulário <xref:System.Windows.Forms.Form.Load> evento e o <xref:System.Windows.Forms.DataGridView> do controle <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="7ebc1-124">Quando o **adicionar** do botão <xref:System.Windows.Forms.Control.Click> é gerado, uma linha nova e vazia é adicionada para o <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="7ebc1-125">Quando o **excluir** do botão <xref:System.Windows.Forms.Control.Click> é gerado, a linha selecionada será excluída, a menos que a linha para novos registros, que permite ao usuário adicionar novas linhas.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="7ebc1-126">Essa linha é sempre a última linha a <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="7ebc1-127">Quando o formulário <xref:System.Windows.Forms.Form.Load> é gerado, o `SetupLayout`, `SetupDataGridView`, e `PopulateDataGridView` são chamados de métodos de utilitário.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="7ebc1-128">Quando o <xref:System.Windows.Forms.DataGridView.CellFormatting> é gerado, cada célula a `Date` coluna é formatada como uma data por extenso, a menos que o valor da célula não pode ser analisado.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="7ebc1-129">Testando o aplicativo</span><span class="sxs-lookup"><span data-stu-id="7ebc1-129">Testing the Application</span></span>  
 <span data-ttu-id="7ebc1-130">Agora, é possível testar o formulário para garantir que ele se comporta da forma esperada.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="7ebc1-131">Para testar o formulário</span><span class="sxs-lookup"><span data-stu-id="7ebc1-131">To test the form</span></span>  
  
-   <span data-ttu-id="7ebc1-132">Pressione F5 para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="7ebc1-133">Você verá um <xref:System.Windows.Forms.DataGridView> controle que exibe as músicas listadas em `PopulateDataGridView`.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="7ebc1-134">Você pode adicionar novas linhas com o botão **Adicionar Linha** e excluir linhas selecionadas com o botão **Excluir Linha**.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="7ebc1-135">O desassociado <xref:System.Windows.Forms.DataGridView> controle é o repositório de dados e seus dados serão independentes de qualquer fonte externa, como um <xref:System.Data.DataSet> ou uma matriz.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7ebc1-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7ebc1-136">Next Steps</span></span>  
 <span data-ttu-id="7ebc1-137">Este aplicativo oferece uma compreensão básica do <xref:System.Windows.Forms.DataGridView> recursos do controle.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="7ebc1-138">Você pode personalizar a aparência e comportamento do <xref:System.Windows.Forms.DataGridView> controle de várias maneiras:</span><span class="sxs-lookup"><span data-stu-id="7ebc1-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="7ebc1-139">Alterar estilos de borda e cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-139">Change border and header styles.</span></span> <span data-ttu-id="7ebc1-140">Para obter mais informações, consulte [Como alterar os estilos de borda e linha de grade no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="7ebc1-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="7ebc1-141">Habilitar ou restringir a entrada do usuário para o <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="7ebc1-142">Para obter mais informações, consulte [Como evitar a adição e a exclusão de linhas no controle DataGridView do Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) e [Como tornar colunas somente leitura no controle DataGridView do Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7ebc1-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="7ebc1-143">Verifique a entrada do usuário para erros relacionados ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-143">Check user input for database-related errors.</span></span> <span data-ttu-id="7ebc1-144">Para obter mais informações, consulte [Instruções passo a passo: identificando erros que ocorrem durante a entrada de dados no controle DataGridView do Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="7ebc1-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="7ebc1-145">Manipule grandes conjuntos de dados usando o modo virtual.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="7ebc1-146">Para obter mais informações, consulte [Passo a passo: implementando o modo virtual no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7ebc1-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="7ebc1-147">Personalize a aparência das células.</span><span class="sxs-lookup"><span data-stu-id="7ebc1-147">Customize the appearance of cells.</span></span> <span data-ttu-id="7ebc1-148">Para obter mais informações, consulte [Como personalizar a aparência de células no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) e [Como definir estilos de célula padrão no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7ebc1-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebc1-149">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7ebc1-149">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="7ebc1-150">Exibindo dados no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ebc1-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="7ebc1-151">Como criar um controle DataGridView não associado dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ebc1-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="7ebc1-152">Modos de exibição de dados no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ebc1-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)