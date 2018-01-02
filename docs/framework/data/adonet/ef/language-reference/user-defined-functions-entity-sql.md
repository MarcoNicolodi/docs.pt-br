---
title: "Funções definidas pelo usuário (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b97834a500328f7853b8a361ec20d7ff06eda3d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="2ea4e-102">Funções definidas pelo usuário (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2ea4e-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="2ea4e-103">Suporte de Entity SQL que chamam funções definidas pelo usuário em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="2ea4e-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="2ea4e-104">Você pode definir essas funções em linha com a consulta (consulte [como: chamar uma função definida pelo usuário](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) ou como parte do modelo conceitual (consulte [como: definir funções de personalizados no modelo conceitual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span><span class="sxs-lookup"><span data-stu-id="2ea4e-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span></span> <span data-ttu-id="2ea4e-105">Funções de modelo conceitual são definidas como um comando de Entity SQL no [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) elemento de um [função](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) elemento no modelo conceitual.</span><span class="sxs-lookup"><span data-stu-id="2ea4e-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) element of a [Function](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="2ea4e-106">Entity SQL permite que você defina funções no comando de consulta próprias.</span><span class="sxs-lookup"><span data-stu-id="2ea4e-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="2ea4e-107">O [função](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operador define as funções embutidas.</span><span class="sxs-lookup"><span data-stu-id="2ea4e-107">The [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="2ea4e-108">Você pode definir várias funções em um único comando, e essas funções podem ter o mesmo nome de função, como as assinaturas de função são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="2ea4e-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="2ea4e-109">Para obter mais informações, consulte [a resolução de sobrecarga de função](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2ea4e-109">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea4e-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2ea4e-110">See Also</span></span>  
 [<span data-ttu-id="2ea4e-111">Funções</span><span class="sxs-lookup"><span data-stu-id="2ea4e-111">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)