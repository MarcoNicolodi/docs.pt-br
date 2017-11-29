---
title: "Método ICorProfilerCallback::UnmanagedToManagedTransition"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.UnmanagedToManagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 45a2ceb53263e317c5c72695d6bc1e93f8f70bbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="ea4a7-102">Método ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="ea4a7-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="ea4a7-103">Notifica o criador de perfil que ocorreu uma transição de código não gerenciado para código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ea4a7-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4a7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ea4a7-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea4a7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ea4a7-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ea4a7-106">[in] A ID da função que está sendo chamada.</span><span class="sxs-lookup"><span data-stu-id="ea4a7-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="ea4a7-107">[in] Um valor de [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeração que indica se a transição ocorreu devido a uma chamada para código gerenciado em código não gerenciado, ou devido a um retorno de uma função não gerenciada chamado por um gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ea4a7-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4a7-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="ea4a7-108">Remarks</span></span>  
 <span data-ttu-id="ea4a7-109">Se o valor de `reason` é COR_PRF_TRANSITION_RETURN e `functionId` é não nulo, a função ID é que a função não gerenciada e nunca foram compilado usando o compilador just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="ea4a7-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="ea4a7-110">Funções não gerenciadas têm algumas informações básicas associadas a eles, como um nome e alguns metadados.</span><span class="sxs-lookup"><span data-stu-id="ea4a7-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="ea4a7-111">Se o valor de `reason` é COR_PRF_TRANSITION_CALL, é possível que a função de chamada (ou seja, a função gerenciada) ainda não foi compilada por JIT.</span><span class="sxs-lookup"><span data-stu-id="ea4a7-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea4a7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea4a7-112">Requirements</span></span>  
 <span data-ttu-id="ea4a7-113">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea4a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea4a7-114">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea4a7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea4a7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea4a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea4a7-116">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea4a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4a7-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ea4a7-117">See Also</span></span>  
 [<span data-ttu-id="ea4a7-118">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ea4a7-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ea4a7-119">Método ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="ea4a7-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [<span data-ttu-id="ea4a7-120">Usando PInvoke explícito no C++ (atributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="ea4a7-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [<span data-ttu-id="ea4a7-121">Usando interop do C++ (PInvoke implícito)</span><span class="sxs-lookup"><span data-stu-id="ea4a7-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)