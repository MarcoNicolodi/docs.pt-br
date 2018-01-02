---
title: Modelo de Dados de Entidade
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69b72a824e6f9468c9b3d86073243d506382e766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model"></a><span data-ttu-id="4a4e8-102">Modelo de Dados de Entidade</span><span class="sxs-lookup"><span data-stu-id="4a4e8-102">Entity Data Model</span></span>
<span data-ttu-id="4a4e8-103">O EDM (Modelo de Dados de Entidade) é um conjunto de conceitos que descrevem a estrutura de dados, independentemente do formato armazenado.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="4a4e8-104">O EDM pede emprestado o modelo de relacionamento entre entidades descrito por Peter Chen em 1976, mas também cria a partir desse modelo e estende seus usos tradicionais.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="4a4e8-105">O EDM resolve os desafios que ocorrem de ter dados armazenados em vários formatos.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="4a4e8-106">Por exemplo, considere um negócio que armazena dados em bancos de dados relacionais, arquivos de texto, arquivos XML, planilhas e relatórios.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="4a4e8-107">Isso representa desafios significativos na modelagem, na criação de aplicativos e no acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="4a4e8-108">Ao criar um aplicativo orientado a dados, o desafio é escrever código eficiente e sustentável sem sacrificar o acesso eficiente a dados, o armazenamento e a escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="4a4e8-109">Quando os dados têm uma estrutura relacional, o acesso a dados, o armazenamento e a escalabilidade são muito eficientes, mas a escrita de código eficiente e sustentável torna-se mais difícil.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="4a4e8-110">Quando os dados têm uma estrutura de objeto, os conflitos são inversos: escrever código eficiente e sustentável sacrifica o acesso a dados eficiente, o armazenamento e a escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="4a4e8-111">Mesmo que o equilíbrio correto entre esses conflitos seja encontrado, novos desafios surgem quando os dados são movidos de um formato para outro.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="4a4e8-112">O Modelo de Dados de Entidade resolve esses desafios descrevendo a estrutura dos dados em termos de entidades e relacionamentos que são independentes de qualquer esquema de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="4a4e8-113">Isso torna o formato de dados armazenado de dados irrelevante para a criação e o desenvolvimento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="4a4e8-114">E, como as entidades e os relacionamentos descrevem a estrutura de dados como é usada em um aplicativo (não o formato armazenado), eles podem evoluir junto com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="4a4e8-115">Um `conceptual model` é uma representação específica da estrutura de dados como entidades e relações, e é definido geralmente em um DSL (linguagem específica do domínio) que implementa os conceitos do EDM.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="4a4e8-116">[Linguagem de definição de esquema conceitual (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) é um exemplo de tal uma linguagem específica de domínio.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="4a4e8-117">Entidades e relacionamentos descritos em um modelo conceitual podem ser consideradas abstrações de objetos e associações em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="4a4e8-118">Isso permite que os desenvolvedores concentrem-se no modelo conceitual sem se preocuparem com o esquema de armazenamento, e permite que eles escrevam o código pensando em eficiência e facilidade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="4a4e8-119">Enquanto isso, os designers de esquema de armazenamento podem se concentrar na eficiência de acesso a dados, armazenamento e escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a4e8-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4a4e8-120">In This Section</span></span>  
 <span data-ttu-id="4a4e8-121">Os tópicos nesta seção descrevem os conceitos do Modelo de Dados de Entidade.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="4a4e8-122">Qualquer DSL que implemente o EDM deve incluir os conceitos descritos aqui.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="4a4e8-123">Observe que o [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa CSDL para definir modelos conceituais.</span><span class="sxs-lookup"><span data-stu-id="4a4e8-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="4a4e8-124">Para obter mais informações, consulte [especificação CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="4a4e8-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="4a4e8-125">Conceitos chave do modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="4a4e8-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="4a4e8-126">Modelo de dados de entidade: Namespaces</span><span class="sxs-lookup"><span data-stu-id="4a4e8-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="4a4e8-127">Modelo de dados de entidade: Tipos de dados primitivos</span><span class="sxs-lookup"><span data-stu-id="4a4e8-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="4a4e8-128">Modelo de dados de entidade: herança</span><span class="sxs-lookup"><span data-stu-id="4a4e8-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="4a4e8-129">extremidade de associação</span><span class="sxs-lookup"><span data-stu-id="4a4e8-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="4a4e8-130">multiplicidade da extremidade da associação</span><span class="sxs-lookup"><span data-stu-id="4a4e8-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="4a4e8-131">conjunto de associações</span><span class="sxs-lookup"><span data-stu-id="4a4e8-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="4a4e8-132">final do conjunto de associação</span><span class="sxs-lookup"><span data-stu-id="4a4e8-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="4a4e8-133">tipo de associação</span><span class="sxs-lookup"><span data-stu-id="4a4e8-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="4a4e8-134">tipo complexo</span><span class="sxs-lookup"><span data-stu-id="4a4e8-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="4a4e8-135">contêiner de entidade</span><span class="sxs-lookup"><span data-stu-id="4a4e8-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="4a4e8-136">chave de entidade</span><span class="sxs-lookup"><span data-stu-id="4a4e8-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="4a4e8-137">conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="4a4e8-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="4a4e8-138">tipo de entidade</span><span class="sxs-lookup"><span data-stu-id="4a4e8-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="4a4e8-139">facet</span><span class="sxs-lookup"><span data-stu-id="4a4e8-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="4a4e8-140">propriedade de chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="4a4e8-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="4a4e8-141">função declarada por modelo</span><span class="sxs-lookup"><span data-stu-id="4a4e8-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="4a4e8-142">função definida pelo modelo</span><span class="sxs-lookup"><span data-stu-id="4a4e8-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="4a4e8-143">propriedade de navegação</span><span class="sxs-lookup"><span data-stu-id="4a4e8-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="4a4e8-144">propriedade</span><span class="sxs-lookup"><span data-stu-id="4a4e8-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="4a4e8-145">restrição de integridade referencial</span><span class="sxs-lookup"><span data-stu-id="4a4e8-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a4e8-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4a4e8-146">See Also</span></span>  
 <span data-ttu-id="4a4e8-147">[ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) (Ferramentas de modelo de dados de entidade do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="4a4e8-147">[ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)</span></span>  
 [<span data-ttu-id="4a4e8-148">Visão geral do arquivo. edmx</span><span class="sxs-lookup"><span data-stu-id="4a4e8-148">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="4a4e8-149">Especificação de CSDL</span><span class="sxs-lookup"><span data-stu-id="4a4e8-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)