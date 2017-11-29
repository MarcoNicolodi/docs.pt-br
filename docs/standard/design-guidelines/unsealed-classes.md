---
title: "Classes não lacradas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f950d8de2681868fe28e09e4b51bd8156cd12e94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="unsealed-classes"></a><span data-ttu-id="5d83b-102">Classes não lacradas</span><span class="sxs-lookup"><span data-stu-id="5d83b-102">Unsealed Classes</span></span>
<span data-ttu-id="5d83b-103">Classes sealed não podem ser herdadas e impedem que extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="5d83b-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="5d83b-104">Por outro lado, que podem ser herdadas de classes são chamados de classes sem lacre.</span><span class="sxs-lookup"><span data-stu-id="5d83b-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="5d83b-105">**✓ CONSIDERE** usar classes não lacradas sem nenhum adicionado membros virtuais ou protegidos como uma ótima maneira de fornecer mais barato ainda muito mais valioso extensibilidade para uma estrutura.</span><span class="sxs-lookup"><span data-stu-id="5d83b-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="5d83b-106">Os desenvolvedores geralmente desejam herdar de classes não lacradas para adicionar membros de conveniência como construtores personalizados, novos métodos ou sobrecargas do método.</span><span class="sxs-lookup"><span data-stu-id="5d83b-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="5d83b-107">Por exemplo, `System.Messaging.MessageQueue` é sem lacre e, portanto, permite aos usuários criar filas personalizadas esse padrão para um caminho de fila particular ou adicione métodos personalizados que simplificam a API para cenários específicos.</span><span class="sxs-lookup"><span data-stu-id="5d83b-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="5d83b-108">Classes são sem lacre por padrão em linguagens de programação mais e isso também é o padrão recomendado para a maioria das classes em estruturas.</span><span class="sxs-lookup"><span data-stu-id="5d83b-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="5d83b-109">A extensibilidade proporcionada pelo tipos não lacrados é muito apreciados por usuários da estrutura e muito baixo custo fornecer devido a custos de teste relativamente baixa associados a tipos não lacrados.</span><span class="sxs-lookup"><span data-stu-id="5d83b-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="5d83b-110">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="5d83b-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5d83b-111">*Reimpressas pela permissão de Pearson educação, Inc. de [diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008, Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5d83b-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d83b-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5d83b-112">See Also</span></span>  
 [<span data-ttu-id="5d83b-113">Diretrizes de design do Framework</span><span class="sxs-lookup"><span data-stu-id="5d83b-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="5d83b-114">Criação de extensibilidade</span><span class="sxs-lookup"><span data-stu-id="5d83b-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="5d83b-115">Lacrar</span><span class="sxs-lookup"><span data-stu-id="5d83b-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)