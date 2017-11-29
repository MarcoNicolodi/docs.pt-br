---
title: "Instruções passo a passo: trabalhando com o controle MaskedTextBox"
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
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06b8ffd2bda9597198d94c99a785c59cc7cc052e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="a0490-102">Instruções passo a passo: trabalhando com o controle MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a0490-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="a0490-103">As tarefas ilustradas neste passo a passo incluem:</span><span class="sxs-lookup"><span data-stu-id="a0490-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="a0490-104">Inicializando o <xref:System.Windows.Forms.MaskedTextBox> controle</span><span class="sxs-lookup"><span data-stu-id="a0490-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="a0490-105">Usando o <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> manipulador de eventos para alertar o usuário quando um caractere não está de acordo com a máscara</span><span class="sxs-lookup"><span data-stu-id="a0490-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="a0490-106">Atribuir um tipo para o <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> propriedade e usando o <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> manipulador de eventos para alertar o usuário quando o valor que ele está tentando confirmar não é válido para o tipo</span><span class="sxs-lookup"><span data-stu-id="a0490-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="a0490-107">Criar o projeto e adicionar um controle</span><span class="sxs-lookup"><span data-stu-id="a0490-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="a0490-108">Adicionar um controle MaskedTextBox ao seu formulário</span><span class="sxs-lookup"><span data-stu-id="a0490-108">To add a MaskedTextBox control to your form</span></span>  
  
1.  <span data-ttu-id="a0490-109">Abrir o formulário no qual você deseja colocar o <xref:System.Windows.Forms.MaskedTextBox> controle.</span><span class="sxs-lookup"><span data-stu-id="a0490-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2.  <span data-ttu-id="a0490-110">Arraste um <xref:System.Windows.Forms.MaskedTextBox> controlar do **caixa de ferramentas** ao formulário.</span><span class="sxs-lookup"><span data-stu-id="a0490-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3.  <span data-ttu-id="a0490-111">Clique com o botão direito do mouse no controle e escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a0490-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="a0490-112">Na janela **Propriedades**, selecione a propriedade **Máscara** e clique no botão de reticências **...** ao lado do nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="a0490-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4.  <span data-ttu-id="a0490-113">Na caixa de diálogo **Máscara de Entrada**, selecione a máscara **Data abreviada** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0490-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5.  <span data-ttu-id="a0490-114">No **propriedades** janela conjunto o <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> propriedade `true`.</span><span class="sxs-lookup"><span data-stu-id="a0490-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="a0490-115">Essa propriedade faz com que um aviso sonoro curto soe sempre que o usuário tentar inserir um caractere que viola a definição da máscara.</span><span class="sxs-lookup"><span data-stu-id="a0490-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="a0490-116">Para obter um resumo dos caracteres que a propriedade de máscara oferece suporte, consulte a seção de comentários do <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="a0490-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="a0490-117">Alertar o usuário de erros de entrada</span><span class="sxs-lookup"><span data-stu-id="a0490-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="a0490-118">Adicionar uma dica de balão para entrada de máscara rejeitada</span><span class="sxs-lookup"><span data-stu-id="a0490-118">Add a balloon tip for rejected mask input</span></span>  
  
1.  <span data-ttu-id="a0490-119">Volte para o **caixa de ferramentas** e adicione um <xref:System.Windows.Forms.ToolTip> ao formulário.</span><span class="sxs-lookup"><span data-stu-id="a0490-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2.  <span data-ttu-id="a0490-120">Criar um manipulador de eventos para o <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> evento que gera a <xref:System.Windows.Forms.ToolTip> quando ocorre um erro de entrada.</span><span class="sxs-lookup"><span data-stu-id="a0490-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="a0490-121">A dica de balão permanece visível por cinco segundos ou até que o usuário clique nele.</span><span class="sxs-lookup"><span data-stu-id="a0490-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="a0490-122">Alertar o usuário que um tipo que não é válido</span><span class="sxs-lookup"><span data-stu-id="a0490-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="a0490-123">Adicionar uma dica de balão para tipos de dados inválidos</span><span class="sxs-lookup"><span data-stu-id="a0490-123">Add a balloon tip for invalid data types</span></span>  
  
1.  <span data-ttu-id="a0490-124">Em sua forma <xref:System.Windows.Forms.Form.Load> manipulador de eventos, atribuir uma <xref:System.Type> objeto que representa o <xref:System.DateTime> de tipo para o <xref:System.Windows.Forms.MaskedTextBox> do controle <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> propriedade:</span><span class="sxs-lookup"><span data-stu-id="a0490-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  <span data-ttu-id="a0490-125">Adicione um manipulador de eventos ao evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:</span><span class="sxs-lookup"><span data-stu-id="a0490-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0490-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a0490-126">See Also</span></span>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [<span data-ttu-id="a0490-127">Controle MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a0490-127">MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)