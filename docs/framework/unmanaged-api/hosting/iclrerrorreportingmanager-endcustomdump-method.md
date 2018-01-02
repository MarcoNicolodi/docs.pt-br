---
title: "Método ICLRErrorReportingManager::EndCustomDump"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.EndCustomDump
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 059ab01d3cc05bac84bb1a4cd8fffc7fc259ed60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="a11c7-102">Método ICLRErrorReportingManager::EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="a11c7-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="a11c7-103">Remove a configuração de despejo de pilha personalizado foi especificada em uma chamada anterior para o [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a11c7-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a11c7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a11c7-104">Syntax</span></span>  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a11c7-105">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="a11c7-105">Return Value</span></span>  
  
|<span data-ttu-id="a11c7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a11c7-106">HRESULT</span></span>|<span data-ttu-id="a11c7-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="a11c7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a11c7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a11c7-108">S_OK</span></span>|<span data-ttu-id="a11c7-109">`EndCustomDump`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="a11c7-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="a11c7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a11c7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a11c7-111">O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a11c7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a11c7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a11c7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a11c7-113">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="a11c7-113">The call timed out.</span></span>|  
|<span data-ttu-id="a11c7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a11c7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a11c7-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a11c7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a11c7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a11c7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a11c7-117">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.</span><span class="sxs-lookup"><span data-stu-id="a11c7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a11c7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a11c7-118">E_FAIL</span></span>|<span data-ttu-id="a11c7-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a11c7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a11c7-120">Depois que um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="a11c7-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a11c7-121">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a11c7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a11c7-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="a11c7-122">Remarks</span></span>  
 <span data-ttu-id="a11c7-123">O `EndCustomDump` método limpa a configuração de despejo de pilha personalizado definida por uma chamada anterior para o `BeginCustomDump` método e libera qualquer estado associado.</span><span class="sxs-lookup"><span data-stu-id="a11c7-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="a11c7-124">Ele deve ser chamado após a conclusão do despejo da pilha personalizado.</span><span class="sxs-lookup"><span data-stu-id="a11c7-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a11c7-125">Falha ao chamar `EndCustomDump` faz com que a memória vazem.</span><span class="sxs-lookup"><span data-stu-id="a11c7-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a11c7-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a11c7-126">Requirements</span></span>  
 <span data-ttu-id="a11c7-127">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a11c7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a11c7-128">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a11c7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a11c7-129">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="a11c7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a11c7-130">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a11c7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11c7-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a11c7-131">See Also</span></span>  
 [<span data-ttu-id="a11c7-132">Estrutura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="a11c7-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="a11c7-133">Enumeração ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="a11c7-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="a11c7-134">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="a11c7-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)