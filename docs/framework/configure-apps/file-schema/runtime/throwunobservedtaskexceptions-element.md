---
title: '&lt;ThrowUnobservedTaskExceptions&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 635270a6461b573663b7719843d81ff2b23e63dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a><span data-ttu-id="21ccc-102">&lt;ThrowUnobservedTaskExceptions&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="21ccc-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span></span>
<span data-ttu-id="21ccc-103">Especifica se as exceções de tarefas sem tratamento devem encerrar um processo em execução.</span><span class="sxs-lookup"><span data-stu-id="21ccc-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="21ccc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="21ccc-104">\<configuration></span></span>  
<span data-ttu-id="21ccc-105">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="21ccc-105">\<runtime></span></span>  
<span data-ttu-id="21ccc-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="21ccc-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ccc-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="21ccc-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21ccc-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="21ccc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="21ccc-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="21ccc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21ccc-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="21ccc-110">Attributes</span></span>  
  
|<span data-ttu-id="21ccc-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="21ccc-111">Attribute</span></span>|<span data-ttu-id="21ccc-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="21ccc-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="21ccc-113">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="21ccc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="21ccc-114">Especifica se as exceções de tarefa não manipulada devem encerrar o processo em execução.</span><span class="sxs-lookup"><span data-stu-id="21ccc-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="21ccc-115">Atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="21ccc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="21ccc-116">Valor</span><span class="sxs-lookup"><span data-stu-id="21ccc-116">Value</span></span>|<span data-ttu-id="21ccc-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="21ccc-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="21ccc-118">Não encerra o processo em execução para uma exceção sem tratamento de tarefa.</span><span class="sxs-lookup"><span data-stu-id="21ccc-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="21ccc-119">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="21ccc-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="21ccc-120">Encerra o processo em execução para uma exceção sem tratamento de tarefa.</span><span class="sxs-lookup"><span data-stu-id="21ccc-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21ccc-121">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="21ccc-121">Child Elements</span></span>  
 <span data-ttu-id="21ccc-122">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="21ccc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21ccc-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="21ccc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="21ccc-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="21ccc-124">Element</span></span>|<span data-ttu-id="21ccc-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="21ccc-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="21ccc-126">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21ccc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="21ccc-127">Contém informações sobre opções de inicialização do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="21ccc-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="21ccc-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="21ccc-128">Remarks</span></span>  
 <span data-ttu-id="21ccc-129">Se uma exceção que é associada com um <xref:System.Threading.Tasks.Task> não está presente, não há nenhum <xref:System.Threading.Tasks.Task.Wait%2A> operação, o pai não está anexada e o <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> propriedade não foi lido a exceção de tarefa é considerada a ser observada.</span><span class="sxs-lookup"><span data-stu-id="21ccc-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="21ccc-130">No [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], por padrão, se um <xref:System.Threading.Tasks.Task> que tem um observada exceção é coletado como lixo, o finalizador lança uma exceção e encerra o processo.</span><span class="sxs-lookup"><span data-stu-id="21ccc-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="21ccc-131">O encerramento do processo é determinado pelo tempo de coleta de lixo e finalização.</span><span class="sxs-lookup"><span data-stu-id="21ccc-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="21ccc-132">Para tornar mais fácil para os desenvolvedores a gravar código assíncrono baseado em tarefas, o [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] altera esse comportamento padrão para exceções observadas.</span><span class="sxs-lookup"><span data-stu-id="21ccc-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="21ccc-133">Observada exceções ainda farão com que o <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento ser gerado, mas por padrão, o processo não terminar.</span><span class="sxs-lookup"><span data-stu-id="21ccc-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="21ccc-134">Em vez disso, a exceção será ignorada após o evento é gerado, independentemente se um manipulador de eventos observa a exceção.</span><span class="sxs-lookup"><span data-stu-id="21ccc-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="21ccc-135">No [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], você pode usar o [ \<ThrowUnobservedTaskExceptions > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) em um arquivo de configuração do aplicativo para habilitar o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] comportamento de gerar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="21ccc-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="21ccc-136">Você também pode especificar o comportamento de exceção em uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="21ccc-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="21ccc-137">Definindo a variável de ambiente `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="21ccc-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="21ccc-138">Definindo o Registro DWORD valor ThrowUnobservedTaskExceptions = 1 no HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Chave de NETFramework.</span><span class="sxs-lookup"><span data-stu-id="21ccc-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21ccc-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="21ccc-139">Example</span></span>  
 <span data-ttu-id="21ccc-140">O exemplo a seguir mostra como habilitar a gerar exceções em tarefas usando um arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="21ccc-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="21ccc-141">Exemplo</span><span class="sxs-lookup"><span data-stu-id="21ccc-141">Example</span></span>  
 <span data-ttu-id="21ccc-142">O exemplo a seguir demonstra como uma exceção não observada é gerada de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="21ccc-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="21ccc-143">O código deve ser executado como um programa lançado funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="21ccc-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="21ccc-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="21ccc-144">See Also</span></span>  
 [<span data-ttu-id="21ccc-145">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="21ccc-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="21ccc-146">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="21ccc-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)