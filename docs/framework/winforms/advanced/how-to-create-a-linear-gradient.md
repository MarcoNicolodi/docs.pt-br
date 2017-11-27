---
title: Como criar um gradiente linear
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
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bbf3b1657a5a6b91ba88a0968b6b92d4e4bdbf0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="158ea-102">Como criar um gradiente linear</span><span class="sxs-lookup"><span data-stu-id="158ea-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="158ea-103">O [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornece gradientes lineares horizontais, verticais e diagonais.</span><span class="sxs-lookup"><span data-stu-id="158ea-103">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="158ea-104">Por padrão, a cor em um gradiente linear muda uniformemente.</span><span class="sxs-lookup"><span data-stu-id="158ea-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="158ea-105">No entanto, você pode personalizar um gradiente linear para que a cor mude de maneira não uniforme.</span><span class="sxs-lookup"><span data-stu-id="158ea-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="158ea-106">O exemplo a seguir preenche uma linha, uma elipse e um retângulo com um pincel de gradiente linear horizontal.</span><span class="sxs-lookup"><span data-stu-id="158ea-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="158ea-107">O <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> construtor recebe quatro argumentos: dois pontos e duas cores.</span><span class="sxs-lookup"><span data-stu-id="158ea-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="158ea-108">O primeiro ponto (0, 10) é associado à primeira cor (vermelho) e o segundo ponto (200, 10) é associado à segunda cor (azul).</span><span class="sxs-lookup"><span data-stu-id="158ea-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="158ea-109">Como seria de esperar, a linha desenhada de (10, 0) a (200, 10) muda gradualmente de vermelho para azul.</span><span class="sxs-lookup"><span data-stu-id="158ea-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="158ea-110">Os 10s nos pontos (50, 10) e (200, 10) não são importantes.</span><span class="sxs-lookup"><span data-stu-id="158ea-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="158ea-111">O que é importante é que os dois pontos têm a mesma segunda coordenada: a linha que os conecta é horizontal.</span><span class="sxs-lookup"><span data-stu-id="158ea-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="158ea-112">A elipse e o retângulo também mudam gradualmente de vermelho para azul conforme a coordenada horizontal vai de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="158ea-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="158ea-113">A ilustração a seguir mostra a linha, a elipse e o retângulo.</span><span class="sxs-lookup"><span data-stu-id="158ea-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="158ea-114">Observe que o gradiente de cores repete-se à medida que a coordenada horizontal aumenta além de 200.</span><span class="sxs-lookup"><span data-stu-id="158ea-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="158ea-115">![Gradiente linear](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="158ea-115">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="158ea-116">Para usar gradientes lineares horizontais</span><span class="sxs-lookup"><span data-stu-id="158ea-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="158ea-117">Passe o vermelho opaco e o azul opaco como o terceiro e o quarto argumentos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="158ea-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="158ea-118">No exemplo anterior, os componentes de cor mudam linearmente conforme você vai de uma coordenada horizontal de 0 para uma coordenada horizontal de 200.</span><span class="sxs-lookup"><span data-stu-id="158ea-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="158ea-119">Por exemplo, um ponto cuja primeira coordenada esteja a meio caminho entre 0 e 200 terá um componente azul a meio caminho entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="158ea-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="158ea-120">O [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] permite ajustar o modo como a cor varia de uma borda de um gradiente para outra.</span><span class="sxs-lookup"><span data-stu-id="158ea-120">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="158ea-121">Suponha que você queira criar um pincel de gradiente que mude de preto para vermelho de acordo com a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="158ea-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="158ea-122">Coordenada horizontal</span><span class="sxs-lookup"><span data-stu-id="158ea-122">Horizontal coordinate</span></span>|<span data-ttu-id="158ea-123">Componentes RGB</span><span class="sxs-lookup"><span data-stu-id="158ea-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="158ea-124">0</span><span class="sxs-lookup"><span data-stu-id="158ea-124">0</span></span>|<span data-ttu-id="158ea-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="158ea-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="158ea-126">40</span><span class="sxs-lookup"><span data-stu-id="158ea-126">40</span></span>|<span data-ttu-id="158ea-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="158ea-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="158ea-128">200</span><span class="sxs-lookup"><span data-stu-id="158ea-128">200</span></span>|<span data-ttu-id="158ea-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="158ea-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="158ea-130">Observe que o componente vermelho está na metade da intensidade quando a coordenada horizontal está a apenas 20% do caminho de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="158ea-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="158ea-131">O exemplo a seguir define o <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> propriedade de um <xref:System.Drawing.Drawing2D.LinearGradientBrush> objeto para associar três intensidades relativas três posições relativas.</span><span class="sxs-lookup"><span data-stu-id="158ea-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="158ea-132">Como na tabela anterior, uma intensidade relativa de 0,5 é associada a uma posição relativa de 0,2.</span><span class="sxs-lookup"><span data-stu-id="158ea-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="158ea-133">O código preenche uma elipse e um retângulo com o pincel de gradiente.</span><span class="sxs-lookup"><span data-stu-id="158ea-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="158ea-134">A ilustração a seguir mostra o retângulo e elipse resultantes.</span><span class="sxs-lookup"><span data-stu-id="158ea-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="158ea-135">![Gradiente linear](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="158ea-135">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="158ea-136">Para personalizar os gradientes lineares</span><span class="sxs-lookup"><span data-stu-id="158ea-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="158ea-137">Passe o preto opaco e o vermelho opaco como o terceiro e o quarto argumentos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="158ea-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="158ea-138">Os gradientes nos exemplos anteriores eram horizontais; ou seja, a cor muda gradualmente à medida que você se move ao longo de qualquer linha horizontal.</span><span class="sxs-lookup"><span data-stu-id="158ea-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="158ea-139">Você também pode definir gradientes verticais e gradientes diagonais.</span><span class="sxs-lookup"><span data-stu-id="158ea-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="158ea-140">O exemplo a seguir passa os pontos (0, 0) e (200, 100) para um <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> construtor.</span><span class="sxs-lookup"><span data-stu-id="158ea-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="158ea-141">A cor azul é associada a (0, 0) e a cor verde é associada a (200, 100).</span><span class="sxs-lookup"><span data-stu-id="158ea-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="158ea-142">Uma linha (com largura da caneta de 10) e uma elipse são preenchidas com o pincel de gradiente linear.</span><span class="sxs-lookup"><span data-stu-id="158ea-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="158ea-143">A ilustração a seguir mostra a linha e a elipse.</span><span class="sxs-lookup"><span data-stu-id="158ea-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="158ea-144">Observe que a cor na elipse muda gradualmente à medida que você se move ao longo de qualquer linha paralela à linha que passa por (0, 0) e (200, 100).</span><span class="sxs-lookup"><span data-stu-id="158ea-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="158ea-145">![Gradiente linear](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="158ea-145">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="158ea-146">Para criar gradientes lineares diagonais</span><span class="sxs-lookup"><span data-stu-id="158ea-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="158ea-147">Passe o azul opaco e o verde opaco como o terceiro e o quarto argumentos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="158ea-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="158ea-148">Consulte também</span><span class="sxs-lookup"><span data-stu-id="158ea-148">See Also</span></span>  
 [<span data-ttu-id="158ea-149">Usando um Pincel de Gradiente para Preencher Formas</span><span class="sxs-lookup"><span data-stu-id="158ea-149">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [<span data-ttu-id="158ea-150">Elementos Gráficos e Desenho nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="158ea-150">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)