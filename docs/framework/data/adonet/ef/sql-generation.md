---
title: "Geração SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 39f31e27f1e62d889df5a40a9ecb554c2547db8f
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2017
---
# <a name="sql-generation"></a><span data-ttu-id="abd9d-102">Geração SQL</span><span class="sxs-lookup"><span data-stu-id="abd9d-102">SQL Generation</span></span>
<span data-ttu-id="abd9d-103">Quando você escreve um provedor para [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], você deve converter árvores de comando de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] em SQL que um base de dados específico, pode compreender como Transact-SQL para SQL Server ou PL/SQL para Oracle.</span><span class="sxs-lookup"><span data-stu-id="abd9d-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="abd9d-104">Nesta seção, você aprenderá como desenvolver um componente de geração SQL (para consultas SELECT) para um provedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="abd9d-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="abd9d-105">Para obter informações sobre como inserir, atualizar e excluir consultas, consulte [modificação de geração de SQL](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="abd9d-105">For information about insert, update, and delete queries, see [Modification SQL Generation](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="abd9d-106">Para entender esta seção, você deve estar familiarizado com [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e o modelo de provedor ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="abd9d-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="abd9d-107">Você também deve entender árvores e <xref:System.Data.Common.CommandTrees.DbExpression>de comando.</span><span class="sxs-lookup"><span data-stu-id="abd9d-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="abd9d-108">A função do módulo de geração SQL</span><span class="sxs-lookup"><span data-stu-id="abd9d-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="abd9d-109">O módulo de geração SQL de um provedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] converte uma determinada árvore de comando de consulta em uma única instrução SQL SELECT que tem como alvo um SQL: a base de dados compliant 1999.</span><span class="sxs-lookup"><span data-stu-id="abd9d-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="abd9d-110">O SQL gerado deve ter como poucas consultas aninhadas possível.</span><span class="sxs-lookup"><span data-stu-id="abd9d-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="abd9d-111">O módulo de geração do SQL não deve simplificar a árvore de comando de consulta de saída.</span><span class="sxs-lookup"><span data-stu-id="abd9d-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="abd9d-112">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] fará isso, por exemplo eliminando join e recolher nós consecutivos de filtro.</span><span class="sxs-lookup"><span data-stu-id="abd9d-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="abd9d-113">A classe de <xref:System.Data.Common.DbProviderServices> é o ponto de partida para acessar a camada de geração SQL para converter árvores de comando em <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="abd9d-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abd9d-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="abd9d-114">In This Section</span></span>  
 [<span data-ttu-id="abd9d-115">A forma das árvores de comando</span><span class="sxs-lookup"><span data-stu-id="abd9d-115">The Shape of the Command Trees</span></span>](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="abd9d-116">Gerando SQL das árvores de comando - práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="abd9d-116">Generating SQL from Command Trees - Best Practices</span></span>](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="abd9d-117">Geração SQL no provedor exemplo</span><span class="sxs-lookup"><span data-stu-id="abd9d-117">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="abd9d-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="abd9d-118">See Also</span></span>  
 [<span data-ttu-id="abd9d-119">Escrevendo um provedor de dados do Entity Framework</span><span class="sxs-lookup"><span data-stu-id="abd9d-119">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)