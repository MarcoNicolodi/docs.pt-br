---
title: "Como desenhar uma linha com terminações"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e2d5a5aba4a7634e0ea8480aa9744a5a7b9721d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="37879-102">Como desenhar uma linha com terminações</span><span class="sxs-lookup"><span data-stu-id="37879-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="37879-103">Você pode desenhar o início ou término de uma linha em uma das várias formas chamadas terminações de linha.</span><span class="sxs-lookup"><span data-stu-id="37879-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="37879-104">oferece suporte a várias terminações de linha, como round, quadrado, losango e ponta de seta.</span><span class="sxs-lookup"><span data-stu-id="37879-104"> supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37879-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="37879-105">Example</span></span>  
 <span data-ttu-id="37879-106">Você pode especificar as terminações de linha para o início de uma linha (início cap), o fim de uma linha final cap () ou os traços de uma linha tracejada (traço cap).</span><span class="sxs-lookup"><span data-stu-id="37879-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="37879-107">O exemplo a seguir desenha uma linha com uma ponta de seta em uma extremidade e uma extremidade redonda na outra extremidade.</span><span class="sxs-lookup"><span data-stu-id="37879-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="37879-108">A ilustração mostra a linha resultante:</span><span class="sxs-lookup"><span data-stu-id="37879-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="37879-109">![Canetas](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="37879-109">![Pens](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="37879-110">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="37879-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="37879-111">Criar um formulário do Windows e controlar o formulário <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="37879-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="37879-112">Cole o código de exemplo para o <xref:System.Windows.Forms.Control.Paint> passando do manipulador de eventos `e` como <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="37879-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37879-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="37879-113">See Also</span></span>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [<span data-ttu-id="37879-114">Elementos Gráficos e Desenho nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37879-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="37879-115">Usando uma caneta para desenhar linhas e formas</span><span class="sxs-lookup"><span data-stu-id="37879-115">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)