---
title: CountdownEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="dc0ba-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="dc0ba-102">CountdownEvent</span></span>
<span data-ttu-id="dc0ba-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>é um primitivo de sincronização que desbloqueia seus threads de espera, depois de ser sinalizado um determinado número de vezes.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="dc0ba-104"><xref:System.Threading.CountdownEvent>foi projetado para cenários em que caso contrário, seria necessário usar um <xref:System.Threading.ManualResetEvent> ou <xref:System.Threading.ManualResetEventSlim> e diminuir manualmente uma variável antes de sinalizar o evento.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="dc0ba-105">Por exemplo, em um cenário de bifurcação/junção, você pode simplesmente criar um <xref:System.Threading.CountdownEvent> que tem uma contagem de sinal de 5 e, em seguida, iniciar cinco itens de trabalho no thread de pool e tem cada chamada de item de trabalho <xref:System.Threading.CountdownEvent.Signal%2A> quando ele for concluído.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="dc0ba-106">Cada chamada para <xref:System.Threading.CountdownEvent.Signal%2A> diminui o sinal de contagem em 1.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="dc0ba-107">No thread principal, a chamada para <xref:System.Threading.CountdownEvent.Wait%2A> será bloqueado até que a contagem de sinal é zero.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc0ba-108">Para o código que não têm para interagir com a sincronização do .NET Framework herdada APIs, considere o uso de <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objetos ou o <xref:System.Threading.Tasks.Parallel.Invoke%2A> método para uma abordagem mais fácil para expressar o paralelismo bifurcado.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="dc0ba-109"><xref:System.Threading.CountdownEvent>tem estes recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="dc0ba-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="dc0ba-110">A operação de espera pode ser cancelada usando tokens de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="dc0ba-111">Sua contagem de sinal pode ser incrementada depois que a instância é criada.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="dc0ba-112">Instâncias podem ser reutilizadas após <xref:System.Threading.CountdownEvent.Wait%2A> foi retornado ao chamar o <xref:System.Threading.CountdownEvent.Reset%2A> método.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="dc0ba-113">Instâncias de expõem um <xref:System.Threading.WaitHandle> para integração com outra APIs de sincronização do .NET Framework, como <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="dc0ba-114">Uso básico</span><span class="sxs-lookup"><span data-stu-id="dc0ba-114">Basic Usage</span></span>  
 <span data-ttu-id="dc0ba-115">O exemplo a seguir demonstra como usar um <xref:System.Threading.CountdownEvent> com <xref:System.Threading.ThreadPool> itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="dc0ba-116">CountdownEvent com cancelamento</span><span class="sxs-lookup"><span data-stu-id="dc0ba-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="dc0ba-117">O exemplo a seguir mostra como cancelar a operação de espera em <xref:System.Threading.CountdownEvent> usando um token de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="dc0ba-118">O padrão básico segue o modelo para cancelamento unificado, introduzida no [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc0ba-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="dc0ba-119">Para obter mais informações, consulte [cancelamento em Threads gerenciados](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ba-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="dc0ba-120">Observe que a operação de espera não cancelar os threads que são a sinalização.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="dc0ba-121">Normalmente, o cancelamento é aplicado a uma operação lógica e que pode incluir a aguardar o evento, bem como todos os itens de trabalho que a espera está sincronizando.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="dc0ba-122">Neste exemplo, cada item de trabalho é passado uma cópia do mesmo token de cancelamento de forma que ele pode responder à solicitação de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="dc0ba-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0ba-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dc0ba-123">See Also</span></span>  
 [<span data-ttu-id="dc0ba-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="dc0ba-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)