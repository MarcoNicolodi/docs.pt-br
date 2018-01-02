---
title: "Como imprimir elementos gráficos no Windows Forms"
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
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f495135b3210f430c887451844bec8b154db33c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="ee628-102">Como imprimir elementos gráficos no Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee628-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="ee628-103">Frequentemente, você desejará imprimir elementos gráficos no seu aplicativo do Windows.</span><span class="sxs-lookup"><span data-stu-id="ee628-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="ee628-104">O <xref:System.Drawing.Graphics> classe fornece métodos para desenhar objetos em um dispositivo, como uma tela ou impressora.</span><span class="sxs-lookup"><span data-stu-id="ee628-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="ee628-105">Imprimir elementos gráficos</span><span class="sxs-lookup"><span data-stu-id="ee628-105">To print graphics</span></span>  
  
1.  <span data-ttu-id="ee628-106">Adicionar um <xref:System.Drawing.Printing.PrintDocument> componente para seu formulário.</span><span class="sxs-lookup"><span data-stu-id="ee628-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="ee628-107">No <xref:System.Drawing.Printing.PrintDocument.PrintPage> manipulador de eventos, use o <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> propriedade o <xref:System.Drawing.Printing.PrintPageEventArgs> classe para instruir a impressora sobre o tipo de gráfico para imprimir.</span><span class="sxs-lookup"><span data-stu-id="ee628-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="ee628-108">O exemplo de código a seguir mostra um manipulador de eventos usado para criar uma elipse azul dentro de um retângulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="ee628-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="ee628-109">O retângulo tem as seguintes posição e dimensões: começando em 100, 150 com uma largura de 250 e altura de 250.</span><span class="sxs-lookup"><span data-stu-id="ee628-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="ee628-110">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ee628-110">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ee628-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ee628-111">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="ee628-112">Suporte à impressão nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee628-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)