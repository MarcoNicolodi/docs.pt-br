---
title: "Padrões comuns de Design"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd2d78e675ebc67cc2e49f5bc7141558d462a3e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="common-design-patterns"></a><span data-ttu-id="0c22d-102">Padrões comuns de Design</span><span class="sxs-lookup"><span data-stu-id="0c22d-102">Common Design Patterns</span></span>
<span data-ttu-id="0c22d-103">Há diversos livros em padrões de software, os idiomas padrão e antipatterns que o assunto muito amplo de padrões de endereço.</span><span class="sxs-lookup"><span data-stu-id="0c22d-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="0c22d-104">Portanto, este capítulo fornece diretrizes e discussões relacionadas a um conjunto muito limitado de padrões que são usados com frequência no design de APIs do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c22d-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c22d-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0c22d-105">In This Section</span></span>  
 [<span data-ttu-id="0c22d-106">Propriedades de dependência</span><span class="sxs-lookup"><span data-stu-id="0c22d-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="0c22d-107">Padrão de Dispose</span><span class="sxs-lookup"><span data-stu-id="0c22d-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="0c22d-108">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="0c22d-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0c22d-109">*Reimpressas pela permissão de Pearson educação, Inc. de [diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008, Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0c22d-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c22d-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0c22d-110">See Also</span></span>  
 [<span data-ttu-id="0c22d-111">Diretrizes de design do Framework</span><span class="sxs-lookup"><span data-stu-id="0c22d-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)