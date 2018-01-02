---
title: "Exceções: a expressão try...with (F#)"
description: "Saiba como usar o F # 'try... com' expressão para manipulação de exceção."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 36721076-95cd-4636-ae43-79dd512bee6c
ms.openlocfilehash: 163dfab49d4aaf23123800246fae2cad33e2257c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="c04c4-104">Exceções: a expressão try...with</span><span class="sxs-lookup"><span data-stu-id="c04c4-104">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="c04c4-105">Este tópico descreve o `try...with` expressão, a expressão que é usada para manipulação de exceções em linguagem F #.</span><span class="sxs-lookup"><span data-stu-id="c04c4-105">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="c04c4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c04c4-106">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="c04c4-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="c04c4-107">Remarks</span></span>
<span data-ttu-id="c04c4-108">O `try...with` expressão é usada para manipular exceções em F #.</span><span class="sxs-lookup"><span data-stu-id="c04c4-108">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="c04c4-109">É semelhante do `try...catch` instrução em c#.</span><span class="sxs-lookup"><span data-stu-id="c04c4-109">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="c04c4-110">Na sintaxe anterior, o código em *expression1* pode gerar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="c04c4-110">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="c04c4-111">O `try...with` expressão retorna um valor.</span><span class="sxs-lookup"><span data-stu-id="c04c4-111">The `try...with` expression returns a value.</span></span> <span data-ttu-id="c04c4-112">Se nenhuma exceção for lançada, toda a expressão retorna o valor de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="c04c4-112">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="c04c4-113">Se uma exceção for lançada, cada *padrão* são comparados por sua vez, com a exceção e para o primeiro padrão de correspondência, correspondente *expressão*, conhecido como o *domanipuladordeexceção*, para essa ramificação é executada, e a expressão geral retorna o valor da expressão nesse manipulador de exceção.</span><span class="sxs-lookup"><span data-stu-id="c04c4-113">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="c04c4-114">Se nenhum padrão corresponder, a exceção propagará a pilha de chamada até que um manipulador correspondente foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="c04c4-114">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="c04c4-115">Os tipos de valores retornados de cada expressão nos manipuladores de exceção devem corresponder ao tipo retornado da expressão no `try` bloco.</span><span class="sxs-lookup"><span data-stu-id="c04c4-115">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="c04c4-116">Frequentemente, o fato de que ocorreu um erro também significa que não há nenhum valor válido que pode ser retornado de expressões em cada manipulador de exceção.</span><span class="sxs-lookup"><span data-stu-id="c04c4-116">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="c04c4-117">Um padrão frequente é ter o tipo da expressão de um tipo de opção.</span><span class="sxs-lookup"><span data-stu-id="c04c4-117">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="c04c4-118">O exemplo de código a seguir ilustra esse padrão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-118">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="c04c4-119">As exceções podem ser exceções .NET, ou podem ser F # exceções.</span><span class="sxs-lookup"><span data-stu-id="c04c4-119">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="c04c4-120">Você pode definir F # exceções usando o `exception` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="c04c4-120">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="c04c4-121">Você pode usar uma variedade de padrões para filtrar o tipo de exceção e outras condições; as opções são resumidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c04c4-121">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="c04c4-122">Padrão</span><span class="sxs-lookup"><span data-stu-id="c04c4-122">Pattern</span></span>|<span data-ttu-id="c04c4-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="c04c4-123">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="c04c4-124">:?</span><span class="sxs-lookup"><span data-stu-id="c04c4-124">:?</span></span> <span data-ttu-id="c04c4-125">*tipo de exceção*</span><span class="sxs-lookup"><span data-stu-id="c04c4-125">*exception-type*</span></span>|<span data-ttu-id="c04c4-126">Corresponde ao tipo de exceção .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="c04c4-126">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="c04c4-127">:?</span><span class="sxs-lookup"><span data-stu-id="c04c4-127">:?</span></span> <span data-ttu-id="c04c4-128">*tipo de exceção* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="c04c4-128">*exception-type* as *identifier*</span></span>|<span data-ttu-id="c04c4-129">Corresponde ao tipo especificado de exceção do .NET, mas oferece a exceção de um valor nomeado.</span><span class="sxs-lookup"><span data-stu-id="c04c4-129">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="c04c4-130">*nome da exceção*(*argumentos*)</span><span class="sxs-lookup"><span data-stu-id="c04c4-130">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="c04c4-131">Corresponde a um tipo de exceção F # e associa os argumentos.</span><span class="sxs-lookup"><span data-stu-id="c04c4-131">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="c04c4-132">*identifier*</span><span class="sxs-lookup"><span data-stu-id="c04c4-132">*identifier*</span></span>|<span data-ttu-id="c04c4-133">Corresponde a qualquer exceção e associa o nome para o objeto de exceção.</span><span class="sxs-lookup"><span data-stu-id="c04c4-133">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="c04c4-134">Equivalente a **:? System. Exception como***identificador*</span><span class="sxs-lookup"><span data-stu-id="c04c4-134">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="c04c4-135">*identificador* quando *condição*</span><span class="sxs-lookup"><span data-stu-id="c04c4-135">*identifier* when *condition*</span></span>|<span data-ttu-id="c04c4-136">Corresponde a qualquer exceção se a condição for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="c04c4-136">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="c04c4-137">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c04c4-137">Examples</span></span>
<span data-ttu-id="c04c4-138">Os exemplos de código a seguir ilustram o uso de vários padrões de manipulador de exceção.</span><span class="sxs-lookup"><span data-stu-id="c04c4-138">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="c04c4-139">O `try...with` construção é uma expressão separada do `try...finally` expressão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-139">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="c04c4-140">Portanto, se seu código requer um `with` bloco e um `finally` bloco, você terá de aninhar as duas expressões.</span><span class="sxs-lookup"><span data-stu-id="c04c4-140">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="c04c4-141">Você pode usar `try...with` nos fluxos de trabalho assíncronos e outras expressões de computação, nesse caso, uma versão personalizada do `try...with` expressão é usada.</span><span class="sxs-lookup"><span data-stu-id="c04c4-141">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="c04c4-142">Para obter mais informações, consulte [fluxos de trabalho assíncronos](../asynchronous-workflows.md), e [expressões de computação](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c04c4-142">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="c04c4-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c04c4-143">See Also</span></span>
[<span data-ttu-id="c04c4-144">Tratamento de Exceção</span><span class="sxs-lookup"><span data-stu-id="c04c4-144">Exception Handling</span></span>](index.md)

[<span data-ttu-id="c04c4-145">Tipos de Exceção</span><span class="sxs-lookup"><span data-stu-id="c04c4-145">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="c04c4-146">Exceções: a expressão `try...finally`</span><span class="sxs-lookup"><span data-stu-id="c04c4-146">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)