---
title: Metarquivos no GDI+
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
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b75ceb08df0454172a000d5d1ad15445f685ddf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="b0343-102">Metarquivos no GDI+</span><span class="sxs-lookup"><span data-stu-id="b0343-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="b0343-103">fornece o <xref:System.Drawing.Imaging.Metafile> de classe para que você possa registrar e exibir metarquivos.</span><span class="sxs-lookup"><span data-stu-id="b0343-103"> provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="b0343-104">Um metarquivo, também chamado de uma imagem de vetor, é uma imagem que é armazenada como uma sequência de comandos e configurações de desenho.</span><span class="sxs-lookup"><span data-stu-id="b0343-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="b0343-105">Os comandos e configurações são registradas em um <xref:System.Drawing.Imaging.Metafile> objeto pode ser armazenado na memória ou salvo em um arquivo ou fluxo.</span><span class="sxs-lookup"><span data-stu-id="b0343-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="b0343-106">Formatos de metarquivos</span><span class="sxs-lookup"><span data-stu-id="b0343-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="b0343-107"> pode exibir metarquivos que foram armazenados nos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="b0343-107"> can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="b0343-108">Metarquivo do Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="b0343-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="b0343-109">EMF (Metarquivo Avançado)</span><span class="sxs-lookup"><span data-stu-id="b0343-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="b0343-110">EMF+</span><span class="sxs-lookup"><span data-stu-id="b0343-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="b0343-111"> pode registrar metarquivos nos formatos EMF e EMF+, mas não no formato WMF.</span><span class="sxs-lookup"><span data-stu-id="b0343-111"> can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="b0343-112">EMF+ é uma extensão de EMF que permite que registros [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sejam armazenados.</span><span class="sxs-lookup"><span data-stu-id="b0343-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="b0343-113">Há duas variações no formato EMF+: Apenas EMF+ e EMF+ Duplo.</span><span class="sxs-lookup"><span data-stu-id="b0343-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="b0343-114">Metarquivos Apenas EMF+ contêm apenas registros [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0343-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="b0343-115">Esses metarquivos podem ser exibidos por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], mas não por [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0343-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="b0343-116">Metarquivos EMF+ Duplos contêm registros [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0343-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="b0343-117">Cada registro [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] em um metarquivo EMF+ Duplo é associado a um registro [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] alternativo.</span><span class="sxs-lookup"><span data-stu-id="b0343-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="b0343-118">Esses metarquivos podem ser exibidos por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ou por [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0343-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="b0343-119">O exemplo a seguir exibe um metarquivo que foi salvo anteriormente como um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0343-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="b0343-120">O metarquivo é exibido com seu canto superior esquerdo em (100, 100).</span><span class="sxs-lookup"><span data-stu-id="b0343-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="b0343-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b0343-121">See Also</span></span>  
 [<span data-ttu-id="b0343-122">Imagens, bitmaps e metarquivos</span><span class="sxs-lookup"><span data-stu-id="b0343-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)