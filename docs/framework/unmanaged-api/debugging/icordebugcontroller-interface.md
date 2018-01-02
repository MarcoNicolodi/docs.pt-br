---
title: ICorDebugController Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController
helpviewer_keywords: ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b1484d6bcfa77b8bf5fe45b2f83d5dcbff02f907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="a7dcc-102">ICorDebugController Interface1</span><span class="sxs-lookup"><span data-stu-id="a7dcc-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="a7dcc-103">Representa um escopo, um <xref:System.Diagnostics.Process> ou um <xref:System.AppDomain>, em que o contexto de execução de código pode ser controlado.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7dcc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a7dcc-104">Methods</span></span>  
  
|<span data-ttu-id="a7dcc-105">Método</span><span class="sxs-lookup"><span data-stu-id="a7dcc-105">Method</span></span>|<span data-ttu-id="a7dcc-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a7dcc-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="a7dcc-107">Esse método é obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="a7dcc-108">Esse método é obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="a7dcc-109">Método continue</span><span class="sxs-lookup"><span data-stu-id="a7dcc-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="a7dcc-110">Retoma a execução de threads gerenciados após uma chamada para [Icordebugcontroller](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="a7dcc-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="a7dcc-111">Método Detach</span><span class="sxs-lookup"><span data-stu-id="a7dcc-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="a7dcc-112">Desanexa o depurador do domínio de aplicativo ou processo.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="a7dcc-113">Método EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="a7dcc-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="a7dcc-114">Obtém um enumerador para os threads gerenciados ativos no processo.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="a7dcc-115">Método HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="a7dcc-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="a7dcc-116">Obtém um valor que indica se qualquer retornos de chamada gerenciados atualmente na fila para o segmento especificado.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="a7dcc-117">Método IsRunning</span><span class="sxs-lookup"><span data-stu-id="a7dcc-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="a7dcc-118">Obtém um valor que indica se os threads do processo estão em execução no momento livremente.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="a7dcc-119">Método SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="a7dcc-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="a7dcc-120">Define o estado de depuração de todos os threads gerenciados no processo.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="a7dcc-121">Método Stop</span><span class="sxs-lookup"><span data-stu-id="a7dcc-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="a7dcc-122">Executa uma parada cooperativa em todos os threads que estão executando o código gerenciado no processo.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="a7dcc-123">Método Terminate</span><span class="sxs-lookup"><span data-stu-id="a7dcc-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="a7dcc-124">Encerra o processo com o código de saída especificado.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7dcc-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="a7dcc-125">Remarks</span></span>  
 <span data-ttu-id="a7dcc-126">Se `ICorDebugController` é controlar um processo, o escopo inclui todos os threads do processo.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="a7dcc-127">Se `ICorDebugController` está controlando a um domínio de aplicativo, o escopo inclui apenas os segmentos de domínio de aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7dcc-128">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="a7dcc-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7dcc-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7dcc-129">Requirements</span></span>  
 <span data-ttu-id="a7dcc-130">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7dcc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7dcc-131">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7dcc-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7dcc-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7dcc-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7dcc-133">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7dcc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7dcc-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a7dcc-134">See Also</span></span>  
 [<span data-ttu-id="a7dcc-135">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="a7dcc-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)