---
title: "Instruções passo a passo: implementando o modo virtual no controle DataGridView dos Windows Forms"
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
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31806d3ed13776e26634914b48bc887297ea4dab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a2899-102">Instruções passo a passo: implementando o modo virtual no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2899-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a2899-103">Quando você deseja exibir grandes quantidades de dados tabulares em uma <xref:System.Windows.Forms.DataGridView> controle, você pode definir o <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propriedade `true` e gerenciar explicitamente a interação do controle com seu repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="a2899-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="a2899-104">Isso permite ajustar o desempenho do controle nessa situação.</span><span class="sxs-lookup"><span data-stu-id="a2899-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="a2899-105">O <xref:System.Windows.Forms.DataGridView> controle fornece vários eventos que você pode manipular para interagir com um armazenamento de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="a2899-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="a2899-106">Este passo a passo orienta você ao longo do processo de implementar esses manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2899-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="a2899-107">O exemplo de código neste tópico usa uma fonte de dados muito simples para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="a2899-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="a2899-108">Em um ambiente de produção, você normalmente carrega apenas as linhas que você precisa exibir em um cache e manipular <xref:System.Windows.Forms.DataGridView> eventos para interagir com e atualizar o cache.</span><span class="sxs-lookup"><span data-stu-id="a2899-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="a2899-109">Para obter mais informações, consulte [Implementando o modo virtual com carregamento de dados Just-In-Time no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="a2899-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="a2899-110">Para copiar o código deste tópico como uma única lista, consulte [Como implementar o modo virtual no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a2899-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="a2899-111">Criando o formulário</span><span class="sxs-lookup"><span data-stu-id="a2899-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="a2899-112">Para implementar o modo virtual</span><span class="sxs-lookup"><span data-stu-id="a2899-112">To implement virtual mode</span></span>  
  
1.  <span data-ttu-id="a2899-113">Criar uma classe que deriva de <xref:System.Windows.Forms.Form> e contém um <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="a2899-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="a2899-114">O código a seguir contém uma inicialização básica.</span><span class="sxs-lookup"><span data-stu-id="a2899-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="a2899-115">Ele declara algumas variáveis que serão usadas em etapas posteriores, fornece um método `Main` e fornece um layout de formulário simples no construtor da classe.</span><span class="sxs-lookup"><span data-stu-id="a2899-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <span data-ttu-id="a2899-116">Implementar um manipulador para o seu formulário <xref:System.Windows.Forms.Form.Load> evento que inicializa o <xref:System.Windows.Forms.DataGridView> controlar e preenche o armazenamento de dados com valores de exemplo.</span><span class="sxs-lookup"><span data-stu-id="a2899-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  <span data-ttu-id="a2899-117">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento que recupera o valor da célula solicitada do armazenamento de dados ou o `Customer` objeto atualmente na edição.</span><span class="sxs-lookup"><span data-stu-id="a2899-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="a2899-118">Esse evento ocorre sempre que o <xref:System.Windows.Forms.DataGridView> controle precisa pintar uma célula.</span><span class="sxs-lookup"><span data-stu-id="a2899-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  <span data-ttu-id="a2899-119">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos que armazena um valor de célula editado no `Customer` objeto que representa a linha editada.</span><span class="sxs-lookup"><span data-stu-id="a2899-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="a2899-120">Esse evento ocorre sempre que o usuário confirma uma alteração de valor da célula.</span><span class="sxs-lookup"><span data-stu-id="a2899-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  <span data-ttu-id="a2899-121">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.NewRowNeeded> que cria um novo evento `Customer` objeto que representa uma linha criada recentemente.</span><span class="sxs-lookup"><span data-stu-id="a2899-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a2899-122">Esse evento ocorre sempre que o usuário insere a linha de novos registros.</span><span class="sxs-lookup"><span data-stu-id="a2899-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  <span data-ttu-id="a2899-123">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.RowValidated> evento que salva linhas novas ou modificadas para o repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="a2899-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="a2899-124">Esse evento ocorre sempre que o usuário altera a linha atual.</span><span class="sxs-lookup"><span data-stu-id="a2899-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  <span data-ttu-id="a2899-125">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento que indica se o <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento ocorrerá quando o usuário sinaliza reverter linha pressionando ESC duas vezes no modo de edição ou uma vez fora do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="a2899-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="a2899-126">Por padrão, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> ocorre após a reversão de linha quando as células na linha atual foram modificadas, a menos que o <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> está definida como `true` no <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2899-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="a2899-127">Esse evento é útil quando o escopo da confirmação é determinado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a2899-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  <span data-ttu-id="a2899-128">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.CancelRowEdit> eventos que descarta os valores a `Customer` objeto que representa a linha atual.</span><span class="sxs-lookup"><span data-stu-id="a2899-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="a2899-129">Esse evento ocorre quando o usuário sinaliza a reversão da linha pressionando ESC duas vezes no modo de edição ou uma vez fora do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="a2899-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="a2899-130">Esse evento não ocorre se nenhuma célula na linha atual ter sido modificada ou se o valor da <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propriedade foi definida `false` em um <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2899-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="a2899-131">Implementar um manipulador para o <xref:System.Windows.Forms.DataGridView.UserDeletingRow> evento que exclui uma existente `Customer` objeto do armazenamento de dados ou descarta um não salvas `Customer` objeto que representa uma linha criada recentemente.</span><span class="sxs-lookup"><span data-stu-id="a2899-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a2899-132">Esse evento ocorre sempre que o usuário exclui uma linha clicando em um cabeçalho de linha e pressionando a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="a2899-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="a2899-133">Implemente uma classe `Customers` simples para representar os itens de dados usados por este exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="a2899-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="a2899-134">Testando o aplicativo</span><span class="sxs-lookup"><span data-stu-id="a2899-134">Testing the Application</span></span>  
 <span data-ttu-id="a2899-135">Agora, é possível testar o formulário para garantir que ele se comporta da forma esperada.</span><span class="sxs-lookup"><span data-stu-id="a2899-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="a2899-136">Para testar o formulário</span><span class="sxs-lookup"><span data-stu-id="a2899-136">To test the form</span></span>  
  
-   <span data-ttu-id="a2899-137">Compile e execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a2899-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="a2899-138">Você verá um <xref:System.Windows.Forms.DataGridView> preenchido com três registros de cliente de controle.</span><span class="sxs-lookup"><span data-stu-id="a2899-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="a2899-139">É possível modificar os valores de várias células em uma linha e pressionar ESC duas vezes no modo de edição e uma vez fora do modo de edição para reverter a linha inteira para seus valores originais.</span><span class="sxs-lookup"><span data-stu-id="a2899-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="a2899-140">Quando você modifica, adiciona ou exclui linhas no controle, objetos `Customer` no armazenamento de dados também são modificados, adicionados ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="a2899-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a2899-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a2899-141">Next Steps</span></span>  
 <span data-ttu-id="a2899-142">Este aplicativo oferece uma compreensão básica dos eventos que você deve tratar para implementar o modo virtual no <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="a2899-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a2899-143">É possível aprimorar esse aplicativo básico de várias maneiras:</span><span class="sxs-lookup"><span data-stu-id="a2899-143">You can improve this basic application in a number of ways:</span></span>  
  
-   <span data-ttu-id="a2899-144">Implemente um armazenamento de dados que armazena em cache os valores de um banco de dados externo.</span><span class="sxs-lookup"><span data-stu-id="a2899-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="a2899-145">O cache deve recuperar e descartar valores conforme necessário, de modo que ele contenha apenas o que é necessário para exibição enquanto consome uma quantidade pequena de memória no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="a2899-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
-   <span data-ttu-id="a2899-146">Ajuste o desempenho do armazenamento de dados dependendo de seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a2899-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="a2899-147">Por exemplo, talvez você queira compensar conexões de rede lentas em vez de limitações de memória do computador cliente usando um tamanho de cache maior e minimizando o número de consultas ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a2899-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="a2899-148">Para obter mais informações armazenar em cache valores de um banco de dados externo, consulte [Como implementar o modo virtual com carregamento de dados Just-In-Time no controle DataGridView dos Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="a2899-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2899-149">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a2899-149">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [<span data-ttu-id="a2899-150">Ajuste de desempenho no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2899-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="a2899-151">Práticas recomendadas para colocação em escala do controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2899-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="a2899-152">Implementando o modo virtual com carregamento de dados Just-In-Time no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2899-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="a2899-153">Como implementar o modo virtual no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2899-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)