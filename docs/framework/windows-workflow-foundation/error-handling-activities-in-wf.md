---
title: "Atividades de manipulação de erro de WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bcb006f649fe0d2a92b4c789c435ba33916d140f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="266b7-102">Atividades de manipulação de erro de WF</span><span class="sxs-lookup"><span data-stu-id="266b7-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="266b7-103"> fornece vários sistema forneceu atividades implementando o tratamento de erro e recuperação.</span><span class="sxs-lookup"><span data-stu-id="266b7-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="266b7-104">[Exceções](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="266b7-104"> [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="266b7-105">Atividades de tratamento de erro</span><span class="sxs-lookup"><span data-stu-id="266b7-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="266b7-106">Qual a exceção a última lançada de uma atividade de `TryCatch` .</span><span class="sxs-lookup"><span data-stu-id="266b7-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="266b7-107">Gerencie uma exceção.</span><span class="sxs-lookup"><span data-stu-id="266b7-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="266b7-108">Implementa manipulação de exceção.</span><span class="sxs-lookup"><span data-stu-id="266b7-108">Implements exception handling.</span></span>|