---
title: Gerando classes de tipo de dados por meio de XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 67b9e239c8b60511caf3989c0b3a1a5d6dcc9b26
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="006f3-102">Gerando classes de tipo de dados por meio de XML</span><span class="sxs-lookup"><span data-stu-id="006f3-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="006f3-103">inclui um novo recurso para gerar classes de tipo de dados de XML.</span><span class="sxs-lookup"><span data-stu-id="006f3-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="006f3-104">Este tópico descreve como gerar automaticamente os tipos de dados para o .NET Blog o RSS feed.</span><span class="sxs-lookup"><span data-stu-id="006f3-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="006f3-105">Obter o XML do .NET Blog RSS feed</span><span class="sxs-lookup"><span data-stu-id="006f3-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="006f3-106">No Internet Explorer, navegue até o [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="006f3-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="006f3-107">A página e selecione **Exibir código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="006f3-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="006f3-108">Copie o texto do feed pressionando **Ctrl + A** para selecionar todo o texto, e **Ctrl + C** para copiar.</span><span class="sxs-lookup"><span data-stu-id="006f3-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="006f3-109">Criar os tipos de dados</span><span class="sxs-lookup"><span data-stu-id="006f3-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="006f3-110">Abra um arquivo de código em que o proxy será usado.</span><span class="sxs-lookup"><span data-stu-id="006f3-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="006f3-111">Esse arquivo deve ser parte de um [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="006f3-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="006f3-112">Posicione o cursor em um local no arquivo fora de todas as classes existentes.</span><span class="sxs-lookup"><span data-stu-id="006f3-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="006f3-113">Selecione **editar**, **Colar especial**, **colar XML como Classes**.</span><span class="sxs-lookup"><span data-stu-id="006f3-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="006f3-114">Classes chamadas `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` e `rssChannelItemGuid` são criados com os membros necessários para acessar os elementos no RSS feed.</span><span class="sxs-lookup"><span data-stu-id="006f3-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="006f3-115">Usando as classes geradas</span><span class="sxs-lookup"><span data-stu-id="006f3-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="006f3-116">Depois que as classes são geradas, eles podem ser usados em código como quaisquer outras classes.</span><span class="sxs-lookup"><span data-stu-id="006f3-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="006f3-117">O exemplo de código a seguir retorna uma nova instância do `rssChannelImage` classe.</span><span class="sxs-lookup"><span data-stu-id="006f3-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```