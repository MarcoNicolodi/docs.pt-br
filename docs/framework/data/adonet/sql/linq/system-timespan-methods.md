---
title: "Métodos de System.TimeSpan"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a32b57488b49e9fd2f4e6342391690b27d7ad825
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="systemtimespan-methods"></a><span data-ttu-id="ca9b8-102">Métodos de System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ca9b8-102">System.TimeSpan Methods</span></span>
<span data-ttu-id="ca9b8-103">Suporte de membro para <xref:System.TimeSpan?displayProperty=nameWithType> depende das versões do .NET Framework e do Microsoft SQL Server que você está usando.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-103">Member support for <xref:System.TimeSpan?displayProperty=nameWithType> greatly depends on the versions of the .NET Framework and Microsoft SQL Server that you are using.</span></span>  
  
 <span data-ttu-id="ca9b8-104">Quando um método, um operador, ou uma propriedade são sem suporte; significa que LINQ to SQL não pode converter o membro para execução no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-104">When a method, operator, or property is unsupported; it means that LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="ca9b8-105">Você pode ainda seja possível usar esses membros no seu código.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-105">You may still be able to use these members in your code.</span></span> <span data-ttu-id="ca9b8-106">No entanto, devem ser avaliado antes que a consulta seja convertida a Transact-SQL ou após os resultados foram recuperados de base de dados.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-106">However, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="previous-limitations"></a><span data-ttu-id="ca9b8-107">Limitações anteriores</span><span class="sxs-lookup"><span data-stu-id="ca9b8-107">Previous Limitations</span></span>  
 <span data-ttu-id="ca9b8-108">Ao usar LINQ to SQL com versões do .NET Framework antes do .NET Framework 3.5 SP1, você não pode mapear campos de base de dados SQL Server a <xref:System.TimeSpan?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-108">When using LINQ to SQL with versions of the .NET Framework prior to .NET Framework 3.5 SP1, you cannot map SQL Server database fields to <xref:System.TimeSpan?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ca9b8-109">No entanto, as operações no <xref:System.TimeSpan> têm suporte porque os valores <xref:System.TimeSpan> podem ser retornados da subtração de <xref:System.DateTime> ou introduzidos em uma expressão como um literal ou uma variável associada.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-109">However, operations on <xref:System.TimeSpan> are supported because <xref:System.TimeSpan> values can be returned from <xref:System.DateTime> subtraction or introduced into an expression as a literal or bound variable.</span></span>  
  
## <a name="supported-systemtimespan-method-support"></a><span data-ttu-id="ca9b8-110">Suporte suporte de método System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ca9b8-110">Supported System.TimeSpan Method Support</span></span>  
 <span data-ttu-id="ca9b8-111">Seguinte LINQ para os métodos suportados SQL-, operadores, e propriedades estão disponíveis para que você as use nas consultas LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-111">The following LINQ to SQL-supported methods, operators, and properties are available for you to use in your LINQ to SQL queries.</span></span> <span data-ttu-id="ca9b8-112">Mapeado uma vez no modelo de objeto ou no arquivo de mapeamento externo, LINQ to SQL permite que você chame muitos dos membros de <xref:System.TimeSpan?displayProperty=nameWithType> em suas consultas LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-112">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call many of the <xref:System.TimeSpan?displayProperty=nameWithType> members inside your LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="ca9b8-113">Métodos suportados de <xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="ca9b8-113">Supported <xref:System.TimeSpan> Methods</span></span>|<span data-ttu-id="ca9b8-114">Operadores de <xref:System.TimeSpan> suportados</span><span class="sxs-lookup"><span data-stu-id="ca9b8-114">Supported <xref:System.TimeSpan> Operators</span></span>|<span data-ttu-id="ca9b8-115">Propriedades suportadas de <xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="ca9b8-115">Supported <xref:System.TimeSpan> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<!--zz <xref:System.TimeSpan.MinValue%2A>-->|  
  
> [!NOTE]
>  <span data-ttu-id="ca9b8-116">A capacidade de mapear <xref:System.TimeSpan?displayProperty=nameWithType> para uma coluna do SQL `TIME` com LINQ to SQL requer o .NET Framework 3.5 SP1 e além.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-116">The ability to map <xref:System.TimeSpan?displayProperty=nameWithType> to a SQL `TIME` column with LINQ to SQL requires the .NET Framework 3.5 SP1 and beyond.</span></span> <span data-ttu-id="ca9b8-117">O tipo de dados SQL `TIME` só está disponível no Microsoft SQL Server 2008 e além.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-117">The SQL `TIME` data type is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
### <a name="addition-and-subtraction"></a><span data-ttu-id="ca9b8-118">Adição e subtração</span><span class="sxs-lookup"><span data-stu-id="ca9b8-118">Addition and Subtraction</span></span>  
 <span data-ttu-id="ca9b8-119">Embora o tipo de CLR <xref:System.TimeSpan?displayProperty=nameWithType> suporte a adição e subtração, o tipo do SQL `TIME` não.</span><span class="sxs-lookup"><span data-stu-id="ca9b8-119">Although the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type does support addition and subtraction, the SQL `TIME` type does not.</span></span> <span data-ttu-id="ca9b8-120">Devido a isso, as consultas LINQ to SQL gerarão erros se tentam a adição e subtração quando eles são mapeadas para o tipo do SQL `TIME` .</span><span class="sxs-lookup"><span data-stu-id="ca9b8-120">Because of this, your LINQ to SQL queries will generate errors if they attempt addition and subtraction when they are mapped to the SQL `TIME` type.</span></span> <span data-ttu-id="ca9b8-121">Você pode encontrar outras considerações para trabalhar com tipos de data e hora do SQL em [mapeamento de tipo CLR SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ca9b8-121">You can find other considerations for working with SQL date and time types in [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9b8-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ca9b8-122">See Also</span></span>  
 [<span data-ttu-id="ca9b8-123">Conceitos de consulta</span><span class="sxs-lookup"><span data-stu-id="ca9b8-123">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="ca9b8-124">Criando o modelo de objeto</span><span class="sxs-lookup"><span data-stu-id="ca9b8-124">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="ca9b8-125">Mapeamento de tipo CLR do SQL</span><span class="sxs-lookup"><span data-stu-id="ca9b8-125">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="ca9b8-126">Funções e tipos de dados</span><span class="sxs-lookup"><span data-stu-id="ca9b8-126">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)