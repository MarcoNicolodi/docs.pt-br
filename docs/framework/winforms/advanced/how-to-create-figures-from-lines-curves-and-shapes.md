---
title: Como criar figuras usando linhas, curvas e formas
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
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b382e0e1a627d7f61ce8ac664ac47d98c3725cad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="cd1cf-102">Como criar figuras usando linhas, curvas e formas</span><span class="sxs-lookup"><span data-stu-id="cd1cf-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="cd1cf-103">Para criar uma figura, construir um <xref:System.Drawing.Drawing2D.GraphicsPath>e, em seguida, chamar métodos, como <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, para adicionar primitivos para o caminho.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd1cf-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cd1cf-104">Example</span></span>  
 <span data-ttu-id="cd1cf-105">Os exemplos de código a seguir criam caminhos que têm figuras:</span><span class="sxs-lookup"><span data-stu-id="cd1cf-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="cd1cf-106">O primeiro exemplo cria um caminho que contém uma figura única.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="cd1cf-107">A figura consiste em um único arco. O arco tem um ângulo de flecha de -180 graus, no sentido anti-horário no sistema de coordenadas padrão.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="cd1cf-108">O segundo exemplo cria um caminho que contém duas figuras.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="cd1cf-109">A primeira figura é um arco seguido por uma linha.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="cd1cf-110">A segunda figura é uma linha seguida por uma curva seguida por uma linha.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="cd1cf-111">A primeira figura foi deixada aberta e a segunda figura está fechada.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd1cf-112">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="cd1cf-112">Compiling the Code</span></span>  
 <span data-ttu-id="cd1cf-113">Os exemplos anteriores são projetados para uso com o Windows Forms e eles requerem <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro do <xref:System.Windows.Forms.Control.Paint> manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cd1cf-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1cf-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cd1cf-114">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="cd1cf-115">Construindo e Desenhando Caminhos</span><span class="sxs-lookup"><span data-stu-id="cd1cf-115">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [<span data-ttu-id="cd1cf-116">Usando uma caneta para desenhar linhas e formas</span><span class="sxs-lookup"><span data-stu-id="cd1cf-116">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)