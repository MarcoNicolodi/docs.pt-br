---
title: "Enumeração NOTIFY_FILTER"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NOTIFY_FILTER
api_location: diasymreader.dll
api_type: COM
f1_keywords: NOTIFY_FILTER
helpviewer_keywords: NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9db03458aab60d28efe52edfd9830da7862fcb8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="4df18-102">Enumeração NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="4df18-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="4df18-103">Identifica os retornos de chamada para funções do depurador.</span><span class="sxs-lookup"><span data-stu-id="4df18-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="4df18-104">Para obter mais informações, consulte o [Inotifysource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4df18-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4df18-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4df18-105">Syntax</span></span>  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="4df18-106">Membros</span><span class="sxs-lookup"><span data-stu-id="4df18-106">Members</span></span>  
  
|<span data-ttu-id="4df18-107">Membro</span><span class="sxs-lookup"><span data-stu-id="4df18-107">Member</span></span>|<span data-ttu-id="4df18-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="4df18-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="4df18-109">Indica que o [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) método deve ser invocado.</span><span class="sxs-lookup"><span data-stu-id="4df18-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="4df18-110">Indica que o [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) método deve ser invocado.</span><span class="sxs-lookup"><span data-stu-id="4df18-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="4df18-111">Indica que o [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) método deve ser invocado.</span><span class="sxs-lookup"><span data-stu-id="4df18-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="4df18-112">Indica que o [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) método deve ser invocado.</span><span class="sxs-lookup"><span data-stu-id="4df18-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="4df18-113">Indica que todos os [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) métodos devem ser chamados.</span><span class="sxs-lookup"><span data-stu-id="4df18-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="4df18-114">Ativa todas as notificações existentes e futuras.</span><span class="sxs-lookup"><span data-stu-id="4df18-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="4df18-115">Indica que nenhum método de notificação deve ser chamado.</span><span class="sxs-lookup"><span data-stu-id="4df18-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4df18-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4df18-116">Requirements</span></span>  
 <span data-ttu-id="4df18-117">**Cabeçalho:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="4df18-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df18-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4df18-118">See Also</span></span>  
 [<span data-ttu-id="4df18-119">Enumerações de armazenamento de símbolo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4df18-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)