---
title: "Acessando recursos do serviço de dados (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c15ca5efcb23fa6705a4fcfa3eac6d6db09fcbad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-data-service-resources-wcf-data-services"></a><span data-ttu-id="e5826-102">Acessando recursos do serviço de dados (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="e5826-102">Accessing Data Service Resources (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="e5826-103">oferece suporte a [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para expor seus dados como um feed com recursos endereçáveis por URIs.</span><span class="sxs-lookup"><span data-stu-id="e5826-103"> supports the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose your data as a feed with resources that are addressable by URIs.</span></span> <span data-ttu-id="e5826-104">Esses recursos são representados de acordo com as convenções de relação de entidade do [modelo de dados de entidade](../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="e5826-104">These resources are represented according to the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md).</span></span> <span data-ttu-id="e5826-105">Nesse modelo, as entidades representam unidades operacionais de dados que são tipos de dados em um domínio de aplicativo, como clientes, pedidos, itens e classes.</span><span class="sxs-lookup"><span data-stu-id="e5826-105">In this model, entities represent operational units of data that are data types in an application domain, such as customers, orders, items, and products.</span></span> <span data-ttu-id="e5826-106">Os dados de entidades são acessados e alterados usando-se a semântica REST (transferência de estado representativo), especificamente os verbos HTTP padrão GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="e5826-106">Entity data is accessed and changed by using the semantics of representational state transfer (REST), specifically the standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span>  
  
## <a name="addressing-resources"></a><span data-ttu-id="e5826-107">Direcionando recursos</span><span class="sxs-lookup"><span data-stu-id="e5826-107">Addressing Resources</span></span>  
 <span data-ttu-id="e5826-108">No [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], você direciona quaisquer dados expostos pelo modelo de dados usando um URI.</span><span class="sxs-lookup"><span data-stu-id="e5826-108">In [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], you address any data exposed by the data model by using a URI.</span></span> <span data-ttu-id="e5826-109">Por exemplo, o URI a seguir retorna um feed que é o conjunto de entidades de clientes, que contém entradas para todas as instâncias do tipo de entidade de cliente:</span><span class="sxs-lookup"><span data-stu-id="e5826-109">For example, the following URI returns a feed that is the Customers entity set, which contains entries for all instances of the Customer entity type:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 <span data-ttu-id="e5826-110">As entidades têm propriedades especiais chamadas chaves de entidade.</span><span class="sxs-lookup"><span data-stu-id="e5826-110">Entities have special properties called entity keys.</span></span> <span data-ttu-id="e5826-111">Uma chave de entidade é usada para identificar exclusivamente uma única entidade em um conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="e5826-111">An entity key is used to uniquely identify a single entity in an entity set.</span></span> <span data-ttu-id="e5826-112">Isso permite que você direcione uma instância específica de um tipo de entidade no conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="e5826-112">This enables you to address a specific instance of an entity type in the entity set.</span></span> <span data-ttu-id="e5826-113">Por exemplo, o URI a seguir retorna uma entrada para uma instância específica de tipo de entidade Customer que tem um valor de chave `ALFKI`:</span><span class="sxs-lookup"><span data-stu-id="e5826-113">For example, the following URI returns an entry for a specific instance of the Customer entity type that has a key value of `ALFKI`:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 <span data-ttu-id="e5826-114">As propriedades primitivas e complexas de uma instância de entidade também podem ser direcionadas individualmente.</span><span class="sxs-lookup"><span data-stu-id="e5826-114">Primitive and complex properties of an entity instance can also be individually addressed.</span></span> <span data-ttu-id="e5826-115">Por exemplo, o seguinte URI retorna um elemento XML que contém o valor da propriedade `ContactName` para um cliente específico:</span><span class="sxs-lookup"><span data-stu-id="e5826-115">For example, the following URI returns an XML element that contains the `ContactName` property value for a specific Customer:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 <span data-ttu-id="e5826-116">Quando você inclui o ponto de extremidade `$value` no URI anterior, somente o valor da propriedade primitiva é retornado na mensagem de resposta.</span><span class="sxs-lookup"><span data-stu-id="e5826-116">When you include the `$value` endpoint in the previous URI, only the value of the primitive property is returned in the response message.</span></span> <span data-ttu-id="e5826-117">O exemplo a seguir retorna apenas a cadeia de caracteres “Maria Anders” sem o elemento XML:</span><span class="sxs-lookup"><span data-stu-id="e5826-117">The following example returns only the string "Maria Anders" without the XML element:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 <span data-ttu-id="e5826-118">As relações entre as entidades são definidas no modelo de dados por associações.</span><span class="sxs-lookup"><span data-stu-id="e5826-118">Relationships between entities are defined in the data model by associations.</span></span> <span data-ttu-id="e5826-119">Essas associações permitem que você direcione entidades relacionadas usando propriedades de navegação de uma instância de entidade.</span><span class="sxs-lookup"><span data-stu-id="e5826-119">These associations enable you to address related entities by using navigation properties of an entity instance.</span></span> <span data-ttu-id="e5826-120">Uma propriedade de navegação pode retornar uma única entidade relacionada, no caso de uma relação muitos-para-um, ou um conjunto de entidades relacionadas, no caso de uma relação um-para-muitos.</span><span class="sxs-lookup"><span data-stu-id="e5826-120">A navigation property can return either a single related entity, in the case of a many-to-one relationship, or a set of related entities, in the case of a one-to-many relationship.</span></span> <span data-ttu-id="e5826-121">Por exemplo, o seguinte URI retorna um feed que é o conjunto de todos os pedidos relacionados a um cliente específico:</span><span class="sxs-lookup"><span data-stu-id="e5826-121">For example, the following URI returns a feed that is the set of all the Orders that are related to a specific Customer:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 <span data-ttu-id="e5826-122">As relações, que são geralmente bidirecionais, são representadas por um par de propriedades de navegação.</span><span class="sxs-lookup"><span data-stu-id="e5826-122">Relationships, which are usually bi-directional, are represented by a pair of navigation properties.</span></span> <span data-ttu-id="e5826-123">Como o inverso da relação mostrada no exemplo anterior, o seguinte URI retorna uma referência à entidade Customer à qual uma entidade Order específica pertence:</span><span class="sxs-lookup"><span data-stu-id="e5826-123">As the reverse of the relationship shown in the previous example, the following URI returns a reference to the Customer entity to which a specific Order entity belongs:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="e5826-124">também permite que você os recursos de endereço com base nos resultados de expressões de consulta.</span><span class="sxs-lookup"><span data-stu-id="e5826-124"> also enables you to address resources based on the results of query expressions.</span></span> <span data-ttu-id="e5826-125">Isso torna possível filtrar conjuntos de recursos com base em uma expressão avaliada.</span><span class="sxs-lookup"><span data-stu-id="e5826-125">This makes it possible to filter sets of resources based on an evaluated expression.</span></span> <span data-ttu-id="e5826-126">Por exemplo, o seguinte URI filtra os recursos para retornar somente os pedidos para o cliente especificado que foram remetidos desde 22 de setembro de 1997:</span><span class="sxs-lookup"><span data-stu-id="e5826-126">For example, the following URI filters the resources to return only the Orders for the specified Customer that have shipped since September 22, 1997:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 <span data-ttu-id="e5826-127">Para obter mais informações, consulte [OData: convenções de URI](http://go.microsoft.com/fwlink/?LinkId=185564).</span><span class="sxs-lookup"><span data-stu-id="e5826-127">For more information, see [OData: URI Conventions](http://go.microsoft.com/fwlink/?LinkId=185564).</span></span>  
  
## <a name="system-query-options"></a><span data-ttu-id="e5826-128">Opções de consulta de sistema</span><span class="sxs-lookup"><span data-stu-id="e5826-128">System Query Options</span></span>  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="e5826-129">define um conjunto de opções de consulta do sistema que você pode usar para executar operações de consulta tradicional em recursos, como filtragem, classificação e paginação.</span><span class="sxs-lookup"><span data-stu-id="e5826-129"> defines a set of system query options that you can use to perform traditional query operations against resources, such as filtering, sorting, and paging.</span></span> <span data-ttu-id="e5826-130">Por exemplo, o URI a seguir retorna o conjunto de todos os `Order` entidades, juntamente com relacionados `Order_Detail` entidades, os códigos postais que não terminam em `100`:</span><span class="sxs-lookup"><span data-stu-id="e5826-130">For example, the following URI returns the set of all the `Order` entities, along with related `Order_Detail` entities, the postal codes of which do not end in `100`:</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 <span data-ttu-id="e5826-131">As entradas no feed retornado também são ordenadas pelo valor da propriedade ShipCity dos pedidos.</span><span class="sxs-lookup"><span data-stu-id="e5826-131">The entries in the returned feed are also ordered by the value of the ShipCity property of the orders.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="e5826-132">suporta as seguintes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] opções de consulta do sistema:</span><span class="sxs-lookup"><span data-stu-id="e5826-132"> supports the following [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] system query options:</span></span>  
  
|<span data-ttu-id="e5826-133">Opção de consulta</span><span class="sxs-lookup"><span data-stu-id="e5826-133">Query Option</span></span>|<span data-ttu-id="e5826-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5826-134">Description</span></span>|  
|------------------|-----------------|  
|`$orderby`|<span data-ttu-id="e5826-135">Define uma ordem de classificação padrão para entidades no feed retornado.</span><span class="sxs-lookup"><span data-stu-id="e5826-135">Defines a default sort order for entities in the returned feed.</span></span> <span data-ttu-id="e5826-136">A consulta a seguir ordena o feed de clientes retornado por região e cidade:</span><span class="sxs-lookup"><span data-stu-id="e5826-136">The following query orders the returned customers feed by county and city:</span></span><br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> <span data-ttu-id="e5826-137">Para obter mais informações, consulte [OData: opção de consulta do sistema OrderBy ($orderby)](http://go.microsoft.com/fwlink/?LinkId=186968).</span><span class="sxs-lookup"><span data-stu-id="e5826-137">For more information, see [OData: OrderBy System Query Option ($orderby)](http://go.microsoft.com/fwlink/?LinkId=186968).</span></span>|  
|`$top`|<span data-ttu-id="e5826-138">Especifica o número de entidades a serem incluídas no feed retornado.</span><span class="sxs-lookup"><span data-stu-id="e5826-138">Specifies the number of entities to include in the returned feed.</span></span> <span data-ttu-id="e5826-139">O exemplo a seguir ignora os 10 primeiros clientes e retorna os 10 seguintes:</span><span class="sxs-lookup"><span data-stu-id="e5826-139">The following example skips the first 10 customers and then returns the next 10:</span></span><br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> <span data-ttu-id="e5826-140">Para obter mais informações, consulte [OData: opção de consulta do sistema superior ($top)](http://go.microsoft.com/fwlink/?LinkId=186969).</span><span class="sxs-lookup"><span data-stu-id="e5826-140">For more information, see [OData: Top System Query Option ($top)](http://go.microsoft.com/fwlink/?LinkId=186969).</span></span>|  
|`$skip`|<span data-ttu-id="e5826-141">Especifica o número de entidades a serem ignoradas antes de começar a retornar entidades no feed.</span><span class="sxs-lookup"><span data-stu-id="e5826-141">Specifies the number of entities to skip before starting to return entities in the feed.</span></span> <span data-ttu-id="e5826-142">O exemplo a seguir ignora os 10 primeiros clientes e retorna os 10 seguintes:</span><span class="sxs-lookup"><span data-stu-id="e5826-142">The following example skips the first 10 customers and then returns the next 10:</span></span><br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> <span data-ttu-id="e5826-143">Para obter mais informações, consulte [OData: opção de consulta de sistema Skip ($skip)](http://go.microsoft.com/fwlink/?LinkId=186971).</span><span class="sxs-lookup"><span data-stu-id="e5826-143">For more information, see [OData: Skip System Query Option ($skip)](http://go.microsoft.com/fwlink/?LinkId=186971).</span></span>|  
|`$filter`|<span data-ttu-id="e5826-144">Define uma expressão que filtra as entidades retornadas no feed com base em critérios específicos.</span><span class="sxs-lookup"><span data-stu-id="e5826-144">Defines an expression that filters the entities returned in the feed based on specific criteria.</span></span> <span data-ttu-id="e5826-145">Esta opção de consulta oferece suporte a um conjunto de operadores de comparação lógicos, operadores aritméticos e funções de consulta predefinidas que são usadas para avaliar a expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="e5826-145">This query option supports a set of logical comparison operators, arithmetic operators, and predefined query functions that are used to evaluate the filter expression.</span></span> <span data-ttu-id="e5826-146">O exemplo a seguir retorna todos os pedidos cujos códigos postais não terminam em 100:</span><span class="sxs-lookup"><span data-stu-id="e5826-146">The following example returns all orders the postal codes of which do not end in 100:</span></span><br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> <span data-ttu-id="e5826-147">Para obter mais informações, consulte [OData: opção de filtro de consulta de sistema ($filter)](http://go.microsoft.com/fwlink/?LinkId=186972).</span><span class="sxs-lookup"><span data-stu-id="e5826-147">For more information, see [OData: Filter System Query Option ($filter)](http://go.microsoft.com/fwlink/?LinkId=186972).</span></span>|  
|`$expand`|<span data-ttu-id="e5826-148">Especifica quais entidades relacionadas são retornadas pela consulta.</span><span class="sxs-lookup"><span data-stu-id="e5826-148">Specifies which related entities are returned by the query.</span></span> <span data-ttu-id="e5826-149">As entidades relacionadas são incluídas como um feed ou uma entrada embutida na entidade retornada pela consulta.</span><span class="sxs-lookup"><span data-stu-id="e5826-149">Related entities are included as either a feed or an entry inline with the entity returned by the query.</span></span> <span data-ttu-id="e5826-150">O exemplo a seguir retorna o pedido do cliente 'ALFKI' junto com os detalhes dos itens de cada ordem:</span><span class="sxs-lookup"><span data-stu-id="e5826-150">The following example returns the order for the customer 'ALFKI' along with the item details for each order:</span></span><br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> <span data-ttu-id="e5826-151">Para obter mais informações, consulte [OData: opção de consulta do sistema expandir ($expand)](http://go.microsoft.com/fwlink/?LinkId=186973).</span><span class="sxs-lookup"><span data-stu-id="e5826-151">For more information, see [OData: Expand System Query Option ($expand)](http://go.microsoft.com/fwlink/?LinkId=186973).</span></span>|  
|`$select`|<span data-ttu-id="e5826-152">Especifica uma projeção que define as propriedades da entidade que são retornadas na projeção.</span><span class="sxs-lookup"><span data-stu-id="e5826-152">Specifies a projection that defines the properties of the entity are returned in the projection.</span></span> <span data-ttu-id="e5826-153">Por padrão, todas as propriedades de uma entidade são retornadas em um feed.</span><span class="sxs-lookup"><span data-stu-id="e5826-153">By default, all properties of an entity are returned in a feed.</span></span> <span data-ttu-id="e5826-154">A seguinte consulta retorna apenas três propriedades da entidade `Customer`:</span><span class="sxs-lookup"><span data-stu-id="e5826-154">The following query returns only three properties of the `Customer` entity:</span></span><br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> <span data-ttu-id="e5826-155">Para obter mais informações, consulte [OData: Selecionar opção de consulta do sistema ($select)](http://go.microsoft.com/fwlink/?LinkID=186076).</span><span class="sxs-lookup"><span data-stu-id="e5826-155">For more information, see [OData: Select System Query Option ($select)](http://go.microsoft.com/fwlink/?LinkID=186076).</span></span>|  
|`$inlinecount`|<span data-ttu-id="e5826-156">Solicitações de que uma contagem do número de entidades retornadas no feed seja incluída no feed.</span><span class="sxs-lookup"><span data-stu-id="e5826-156">Requests that a count of the number of entities returned in the feed be included with the feed.</span></span> <span data-ttu-id="e5826-157">Para obter mais informações, consulte [OData: opção de consulta Inlinecount System ($inlinecount)](http://go.microsoft.com/fwlink/?LinkId=186975).</span><span class="sxs-lookup"><span data-stu-id="e5826-157">For more information, see [OData: Inlinecount System Query Option ($inlinecount)](http://go.microsoft.com/fwlink/?LinkId=186975).</span></span>|  
  
## <a name="addressing-relationships"></a><span data-ttu-id="e5826-158">Direcionando relações</span><span class="sxs-lookup"><span data-stu-id="e5826-158">Addressing Relationships</span></span>  
 <span data-ttu-id="e5826-159">Além de abordar os conjuntos de entidades e instâncias de entidade, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] também permite que você resolva as associações que representam relações entre entidades.</span><span class="sxs-lookup"><span data-stu-id="e5826-159">In addition to addressing entity sets and entity instances, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] also enables you to address the associations that represent relationships between entities.</span></span> <span data-ttu-id="e5826-160">Essa funcionalidade é necessária para que seja possível criar ou alterar uma relação entre duas instâncias de entidade, como o remetente que está relacionado a um determinado pedido no banco de dados de exemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="e5826-160">This functionality is required to be able to create or change a relationship between two entity instances, such as the shipper that is related to a given order in the Northwind sample database.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="e5826-161">oferece suporte a um `$link` operador para tratar especificamente as associações entre entidades.</span><span class="sxs-lookup"><span data-stu-id="e5826-161"> supports a `$link` operator to specifically address the associations between entities.</span></span> <span data-ttu-id="e5826-162">Por exemplo, o URI a seguir é especificado em uma mensagem de solicitação PUT HTTP para alterar o remetente do pedido especificado para um novo remetente.</span><span class="sxs-lookup"><span data-stu-id="e5826-162">For example, the following URI is specified in an HTTP PUT request message to change the shipper for the specified order to a new shipper.</span></span>  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 <span data-ttu-id="e5826-163">Para obter mais informações, consulte [OData: endereçamento Links entre entradas](http://go.microsoft.com/fwlink/?LinkId=187351).</span><span class="sxs-lookup"><span data-stu-id="e5826-163">For more information, see [OData: Addressing Links between Entries](http://go.microsoft.com/fwlink/?LinkId=187351).</span></span>  
  
## <a name="consuming-the-returned-feed"></a><span data-ttu-id="e5826-164">Consumindo o feed retornado</span><span class="sxs-lookup"><span data-stu-id="e5826-164">Consuming the Returned Feed</span></span>  
 <span data-ttu-id="e5826-165">O URI de um [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] recurso permite que você expostos pelo serviço de dados de entidade de endereço.</span><span class="sxs-lookup"><span data-stu-id="e5826-165">The URI of an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] resource enables you to address entity data exposed by the service.</span></span> <span data-ttu-id="e5826-166">Quando você inserir um URI para o campo de endereço de um navegador da Web, um [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed representação do recurso solicitado é retornada.</span><span class="sxs-lookup"><span data-stu-id="e5826-166">When you enter a URI into the address field of a Web browser, a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed representation of the requested resource is returned.</span></span> <span data-ttu-id="e5826-167">Para obter mais informações, consulte o [WCF Data Services Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5826-167">For more information, see the [WCF Data Services Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="e5826-168">Embora um navegador da Web pode ser útil para testar se um recurso de serviço de dados retorna os dados esperados, serviços de dados de produção que podem criar, atualizar e excluir dados também são geralmente acessados pelo código do aplicativo ou em uma página da Web as linguagens de scripts.</span><span class="sxs-lookup"><span data-stu-id="e5826-168">Although a Web browser may be useful for testing that a data service resource returns the expected data, production data services that can also create, update, and delete data are generally accessed by application code or scripting languages in a Web page.</span></span> <span data-ttu-id="e5826-169">Para obter mais informações, consulte [usando um serviço de dados em um aplicativo cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5826-169">For more information, see [Using a Data Service in a Client Application](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5826-170">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e5826-170">See Also</span></span>  
 [<span data-ttu-id="e5826-171">Site do Protocolo Open Data</span><span class="sxs-lookup"><span data-stu-id="e5826-171">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=182204)