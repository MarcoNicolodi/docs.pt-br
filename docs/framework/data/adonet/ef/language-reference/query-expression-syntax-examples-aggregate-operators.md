---
title: "Consulte exemplos de sintaxe de expressão: Operadores agregados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 565c6dacdcfdcce24dfa1de7d286679a5918a694
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="ceb28-102">Consulte exemplos de sintaxe de expressão: Operadores agregados</span><span class="sxs-lookup"><span data-stu-id="ceb28-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="ceb28-103">Os exemplos neste tópico demonstram como usar o <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, e <xref:System.Linq.Enumerable.Sum%2A> métodos para consultar o [modelo de vendas do AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) usando sintaxe de expressão de consulta.</span><span class="sxs-lookup"><span data-stu-id="ceb28-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="ceb28-104">O Modelo de vendas AdventureWorks usado nesses exemplos é criado a partir das tabelas Contact, Address, Product, SalesOrderHeader e SalesOrderDetail no banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ceb28-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ceb28-105">Os exemplos neste tópico usam o seguinte `using` / `Imports` instruções:</span><span class="sxs-lookup"><span data-stu-id="ceb28-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="ceb28-106">Média</span><span class="sxs-lookup"><span data-stu-id="ceb28-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="ceb28-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-107">Example</span></span>  
 <span data-ttu-id="ceb28-108">O exemplo a seguir usa o método <xref:System.Linq.Enumerable.Average%2A> para localizar o preço médio da lista de produtos de cada estilo.</span><span class="sxs-lookup"><span data-stu-id="ceb28-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="ceb28-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-109">Example</span></span>  
 <span data-ttu-id="ceb28-110">O exemplo a seguir usa <xref:System.Linq.Enumerable.Average%2A> para obter o total vencido médio para cada identificação de contatos</span><span class="sxs-lookup"><span data-stu-id="ceb28-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="ceb28-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-111">Example</span></span>  
 <span data-ttu-id="ceb28-112">O exemplo a seguir usa <xref:System.Linq.Enumerable.Average%2A> para obter os pedidos com o total vencido médio para cada contato.</span><span class="sxs-lookup"><span data-stu-id="ceb28-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="ceb28-113">Contagem</span><span class="sxs-lookup"><span data-stu-id="ceb28-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="ceb28-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-114">Example</span></span>  
 <span data-ttu-id="ceb28-115">O exemplo a seguir usa <xref:System.Linq.Enumerable.Count%2A> para retornar uma lista de IDs de contato e quantos pedidos cada um possui.</span><span class="sxs-lookup"><span data-stu-id="ceb28-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="ceb28-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-116">Example</span></span>  
 <span data-ttu-id="ceb28-117">O exemplo a seguir agrupa produtos pela cor e usa <xref:System.Linq.Enumerable.Count%2A> para retornar o número de produtos em cada grupo de cor.</span><span class="sxs-lookup"><span data-stu-id="ceb28-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="ceb28-118">Máx.</span><span class="sxs-lookup"><span data-stu-id="ceb28-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="ceb28-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-119">Example</span></span>  
 <span data-ttu-id="ceb28-120">O exemplo a seguir usa o método <xref:System.Linq.Enumerable.Max%2A> para obter o maior valor total para cada ID de contato.</span><span class="sxs-lookup"><span data-stu-id="ceb28-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="ceb28-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-121">Example</span></span>  
 <span data-ttu-id="ceb28-122">O exemplo a seguir usa o método <xref:System.Linq.Enumerable.Max%2A> para obter os pedidos com o maior valor total para cada ID de contato.</span><span class="sxs-lookup"><span data-stu-id="ceb28-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="ceb28-123">Mín.</span><span class="sxs-lookup"><span data-stu-id="ceb28-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="ceb28-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-124">Example</span></span>  
 <span data-ttu-id="ceb28-125">O exemplo a seguir usa o método <xref:System.Linq.Enumerable.Min%2A> para obter o menor valor total para cada ID de contato.</span><span class="sxs-lookup"><span data-stu-id="ceb28-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="ceb28-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-126">Example</span></span>  
 <span data-ttu-id="ceb28-127">O exemplo a seguir usa o método <xref:System.Linq.Enumerable.Min%2A> para obter os pedidos com o menor valor total para cada contato.</span><span class="sxs-lookup"><span data-stu-id="ceb28-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="ceb28-128">Sum</span><span class="sxs-lookup"><span data-stu-id="ceb28-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="ceb28-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ceb28-129">Example</span></span>  
 <span data-ttu-id="ceb28-130">O exemplo a seguir usa o método <xref:System.Linq.Enumerable.Sum%2A> para obter o valor total para cada ID de contato.</span><span class="sxs-lookup"><span data-stu-id="ceb28-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="ceb28-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ceb28-131">See Also</span></span>  
 [<span data-ttu-id="ceb28-132">Consultas no LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ceb28-132">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)