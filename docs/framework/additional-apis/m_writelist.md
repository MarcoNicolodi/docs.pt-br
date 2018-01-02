---
title: Campo Connection.m_WriteList
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.Connection.m_WriteList
api_location: System.dll
api_type: Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3849fdd327923e480cd88c932cfdce6580d3f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="b436f-102">Connection.m\_WriteList campo</span><span class="sxs-lookup"><span data-stu-id="b436f-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="b436f-103">`Connection.m_WriteList`é um <xref:System.Collections.ArrayList> de <xref:System.Net.HttpWebRequest> objetos que são enfileirados para serem enviados em HTTP.</span><span class="sxs-lookup"><span data-stu-id="b436f-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="b436f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b436f-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="b436f-105">O `Connection.m_WriteList` campo é privado e não se destina a ser usado diretamente no seu código.</span><span class="sxs-lookup"><span data-stu-id="b436f-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="b436f-106">Microsoft não suporta o uso desse campo em um aplicativo de produção sob nenhuma circunstância.</span><span class="sxs-lookup"><span data-stu-id="b436f-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b436f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b436f-107">Requirements</span></span>

<span data-ttu-id="b436f-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b436f-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b436f-109">**Assembly:** sistema (em System. dll)</span><span class="sxs-lookup"><span data-stu-id="b436f-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="b436f-110">**Versões do .NET framework:** disponível desde o 2.0.</span><span class="sxs-lookup"><span data-stu-id="b436f-110">**.NET Framework versions:** Available since 2.0.</span></span>