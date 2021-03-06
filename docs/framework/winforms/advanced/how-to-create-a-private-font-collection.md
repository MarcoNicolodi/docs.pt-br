---
title: Como criar uma coleção de fontes privada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 824d42c40b07e8662395e7a1286b9a5a6112c415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523072"
---
# <a name="how-to-create-a-private-font-collection"></a>Como criar uma coleção de fontes privada
O <xref:System.Drawing.Text.PrivateFontCollection> classe herda o <xref:System.Drawing.Text.FontCollection> classe base abstrata. Você pode usar um <xref:System.Drawing.Text.PrivateFontCollection> objeto para manter um conjunto de fontes especificamente para o seu aplicativo. Uma coleção de fontes privada pode incluir fontes do sistema instalado, bem como as fontes que não foram instaladas no computador. Para adicionar um arquivo de fonte para uma coleção de fontes privadas, chame o <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> método de um <xref:System.Drawing.Text.PrivateFontCollection> objeto.  
  
 O <xref:System.Drawing.Text.FontCollection.Families%2A> propriedade de um <xref:System.Drawing.Text.PrivateFontCollection> objeto contém uma matriz de <xref:System.Drawing.FontFamily> objetos.  
  
 A quantidade de famílias de fonte em uma coleção de fontes privada não é necessariamente a mesma que a quantidade de arquivos de fonte que foram adicionados à coleção. Por exemplo, suponha que os arquivos ArialBd.tff, Times.tff e TimesBd.tff foram adicionados a uma coleção. Haverá três arquivos, mas somente duas famílias na coleção, pois Times.tff e TimesBd.tff pertencem à mesma família.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir adiciona os seguintes arquivos de fonte de três para um <xref:System.Drawing.Text.PrivateFontCollection> objeto:  
  
-   C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)  
  
-   C:\\*systemroot*\Fonts\CourBI.tff (Courier New, negrito e itálico)  
  
-   C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, negrito)  
  
 O código recupera uma matriz de <xref:System.Drawing.FontFamily> de objetos a partir de <xref:System.Drawing.Text.FontCollection.Families%2A> propriedade do <xref:System.Drawing.Text.PrivateFontCollection> objeto.  
  
 Para cada <xref:System.Drawing.FontFamily> objeto na coleção, o código chama o <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método para determinar se vários estilos (normal, negrito, itálico, negrito e itálico, sublinhado e riscado) estão disponíveis. Os argumentos transmitidos para o <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método são membros de <xref:System.Drawing.FontStyle> enumeração.  
  
 Se uma combinação de determinada família/estilo estiver disponível, um <xref:System.Drawing.Font> objeto é construído usando essa família e estilo. O primeiro argumento passado para o <xref:System.Drawing.Font.%23ctor%2A> construtor é o nome de família de fonte (não um <xref:System.Drawing.FontFamily> objeto como é o caso para outras variações do <xref:System.Drawing.Font.%23ctor%2A> construtor). Após o <xref:System.Drawing.Font> objeto for construído, ele é passado para o <xref:System.Drawing.Graphics.DrawString%2A> método o <xref:System.Drawing.Graphics> classe para exibir o nome da família junto com o nome do estilo.  
  
 A saída do código a seguir é semelhante à saída mostrada na ilustração a seguir.  
  
 ![Texto de Fontes](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff (adicionada à coleção de fontes privadas no exemplo de código a seguir) é o arquivo de fonte do estilo regular da fonte Arial. No entanto, observe que a saída de programa mostra vários estilos disponíveis além de regular para família de fonte Arial. Isso ocorre porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pode simular os estilos negrito, itálico e negrito e itálico do estilo normal. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] também pode produzir sublinhados e riscados do estilo regular.  
  
 Da mesma forma, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pode simular o estilo negrito e itálico do estilo negrito ou do estilo itálico. A saída do programa mostra que o estilo negrito e itálico está disponível para a família Times, embora TimesBd.tff (Times New Roman, negrito) seja o único arquivo Times na coleção.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 O exemplo anterior é projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [Usando fontes e texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
