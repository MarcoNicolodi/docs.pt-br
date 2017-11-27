---
title: "Enumeração CREATE_ASM_NAME_OBJ_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CREATE_ASM_NAME_OBJ_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords: CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4982b33643d855be4b8cace59f1c5cac4201d5ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="e384c-102">Enumeração CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e384c-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="e384c-103">Especifica os atributos de uma [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto quando ele é construído pelo [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) função.</span><span class="sxs-lookup"><span data-stu-id="e384c-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e384c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e384c-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e384c-105">Membros</span><span class="sxs-lookup"><span data-stu-id="e384c-105">Members</span></span>  
  
|<span data-ttu-id="e384c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e384c-106">Member</span></span>|<span data-ttu-id="e384c-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="e384c-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="e384c-108">Indica que o parâmetro passado é uma identidade textual.</span><span class="sxs-lookup"><span data-stu-id="e384c-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="e384c-109">Define alguns valores padrão.</span><span class="sxs-lookup"><span data-stu-id="e384c-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="e384c-110">Verifica a regra de assembly friend (somente o nome e a chave pública).</span><span class="sxs-lookup"><span data-stu-id="e384c-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="e384c-111">Esse membro é somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e384c-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="e384c-112">Uma combinação da `CANOF_PARSE_DISPLAY_NAME` e `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` sinalizadores.</span><span class="sxs-lookup"><span data-stu-id="e384c-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="e384c-113">Esse membro é somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e384c-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e384c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e384c-114">Requirements</span></span>  
 <span data-ttu-id="e384c-115">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e384c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e384c-116">**Cabeçalho:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e384c-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e384c-117">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e384c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e384c-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e384c-118">See Also</span></span>  
 [<span data-ttu-id="e384c-119">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="e384c-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="e384c-120">Função CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="e384c-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [<span data-ttu-id="e384c-121">Enumerações de fusão</span><span class="sxs-lookup"><span data-stu-id="e384c-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)