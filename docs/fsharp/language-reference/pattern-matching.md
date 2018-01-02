---
title: "Correspondência padrão (F#)"
description: "Saiba como os padrões são usados em F # para comparar dados com estruturas lógicas, decompor dados em partes constituintes ou extrair informações de dados."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5562ee98-e2f1-4dcd-8e2f-16ae27baaade
ms.openlocfilehash: 7c7a3110a8f34c0c96c12d4584010a9ac4b485fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="pattern-matching"></a><span data-ttu-id="c0748-104">Correspondência padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-104">Pattern Matching</span></span>

<span data-ttu-id="c0748-105">Os padrões são regras de transformação de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0748-105">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="c0748-106">Eles são usados em toda a linguagem F # para comparar dados com uma estrutura lógica ou estruturas, decompor dados em partes constituintes ou extrair informações de dados de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="c0748-106">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>


## <a name="remarks"></a><span data-ttu-id="c0748-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="c0748-107">Remarks</span></span>
<span data-ttu-id="c0748-108">Padrões são usados em muitas construções de linguagem, como o `match` expressão.</span><span class="sxs-lookup"><span data-stu-id="c0748-108">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="c0748-109">Eles são usados quando você estiver processando os argumentos para funções na `let` associações, as expressões lambda e no manipulador de exceção associado a `try...with` expressão.</span><span class="sxs-lookup"><span data-stu-id="c0748-109">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="c0748-110">Para obter mais informações, consulte [correspondência expressões](match-expressions.md), [associações let](functions/let-bindings.md), [expressões Lambda: A `fun` palavra-chave](functions/lambda-expressions-the-fun-keyword.md), e [exceções: A `try...with` Expressão](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c0748-110">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="c0748-111">Por exemplo, o `match` expressão, o *padrão* é o que segue o símbolo de pipe.</span><span class="sxs-lookup"><span data-stu-id="c0748-111">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="c0748-112">Cada padrão atua como uma regra para transformar a entrada de algum modo.</span><span class="sxs-lookup"><span data-stu-id="c0748-112">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="c0748-113">No `match` expressão, cada padrão é examinado por sua vez, para ver se os dados de entrada serão compatíveis com o padrão.</span><span class="sxs-lookup"><span data-stu-id="c0748-113">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="c0748-114">Se uma correspondência for encontrada, a expressão resultante é executada.</span><span class="sxs-lookup"><span data-stu-id="c0748-114">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="c0748-115">Se uma correspondência não for encontrada, a próxima regra padrão será testada.</span><span class="sxs-lookup"><span data-stu-id="c0748-115">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="c0748-116">Opcional quando *condição* parte é explicada em [correspondência expressões](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c0748-116">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="c0748-117">Padrões suportados são mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0748-117">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="c0748-118">Em tempo de execução, a entrada é testada em relação a cada um dos seguintes padrões na ordem listada na tabela e padrões são aplicadas recursivamente, do primeiro ao último como aparecem no seu código e da esquerda para a direita para os padrões em cada linha.</span><span class="sxs-lookup"><span data-stu-id="c0748-118">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="c0748-119">Nome</span><span class="sxs-lookup"><span data-stu-id="c0748-119">Name</span></span>|<span data-ttu-id="c0748-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0748-120">Description</span></span>|<span data-ttu-id="c0748-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c0748-121">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="c0748-122">Padrão de constante</span><span class="sxs-lookup"><span data-stu-id="c0748-122">Constant pattern</span></span>|<span data-ttu-id="c0748-123">Qualquer numéricos, caractere ou cadeia de caracteres literal, uma constante de enumeração ou um identificador de literal definido</span><span class="sxs-lookup"><span data-stu-id="c0748-123">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="c0748-124">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="c0748-124">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="c0748-125">Padrão de identificador</span><span class="sxs-lookup"><span data-stu-id="c0748-125">Identifier pattern</span></span>|<span data-ttu-id="c0748-126">Um valor de caso de uma união discriminada, um rótulo de exceção ou uma ocorrência do padrão ativo</span><span class="sxs-lookup"><span data-stu-id="c0748-126">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="c0748-127">Padrão de variável</span><span class="sxs-lookup"><span data-stu-id="c0748-127">Variable pattern</span></span>|<span data-ttu-id="c0748-128">*identifier*</span><span class="sxs-lookup"><span data-stu-id="c0748-128">*identifier*</span></span>|`a`|
|<span data-ttu-id="c0748-129">`as`padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-129">`as` pattern</span></span>|<span data-ttu-id="c0748-130">*padrão de* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="c0748-130">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="c0748-131">OU padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-131">OR pattern</span></span>|<span data-ttu-id="c0748-132">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="c0748-132">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="c0748-133">E o padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-133">AND pattern</span></span>|<span data-ttu-id="c0748-134">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="c0748-134">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="c0748-135">Padrão Cons</span><span class="sxs-lookup"><span data-stu-id="c0748-135">Cons pattern</span></span>|<span data-ttu-id="c0748-136">*identificador* :: *identificador da lista*</span><span class="sxs-lookup"><span data-stu-id="c0748-136">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="c0748-137">Padrão de lista</span><span class="sxs-lookup"><span data-stu-id="c0748-137">List pattern</span></span>|<span data-ttu-id="c0748-138">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="c0748-138">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="c0748-139">Padrão de matriz</span><span class="sxs-lookup"><span data-stu-id="c0748-139">Array pattern</span></span>|<span data-ttu-id="c0748-140">[&#124; *pattern_1*;...; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="c0748-140">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="c0748-141">Padrão entre parênteses</span><span class="sxs-lookup"><span data-stu-id="c0748-141">Parenthesized pattern</span></span>|<span data-ttu-id="c0748-142">( *padrão* )</span><span class="sxs-lookup"><span data-stu-id="c0748-142">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="c0748-143">Padrão de tupla</span><span class="sxs-lookup"><span data-stu-id="c0748-143">Tuple pattern</span></span>|<span data-ttu-id="c0748-144">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="c0748-144">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="c0748-145">Padrão de registro</span><span class="sxs-lookup"><span data-stu-id="c0748-145">Record pattern</span></span>|<span data-ttu-id="c0748-146">{ *identifier1* = *pattern_1*;...; *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="c0748-146">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="c0748-147">Padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="c0748-147">Wildcard pattern</span></span>|<span data-ttu-id="c0748-148">_</span><span class="sxs-lookup"><span data-stu-id="c0748-148">_</span></span>|`_`|
|<span data-ttu-id="c0748-149">Padrão junto com a anotação de tipo</span><span class="sxs-lookup"><span data-stu-id="c0748-149">Pattern together with type annotation</span></span>|<span data-ttu-id="c0748-150">*padrão de* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="c0748-150">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="c0748-151">Padrão de teste de tipo</span><span class="sxs-lookup"><span data-stu-id="c0748-151">Type test pattern</span></span>|<span data-ttu-id="c0748-152">:?</span><span class="sxs-lookup"><span data-stu-id="c0748-152">:?</span></span> <span data-ttu-id="c0748-153">*tipo* [como *identificador* ]</span><span class="sxs-lookup"><span data-stu-id="c0748-153">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="c0748-154">Padrão nulo</span><span class="sxs-lookup"><span data-stu-id="c0748-154">Null pattern</span></span>|<span data-ttu-id="c0748-155">nulo</span><span class="sxs-lookup"><span data-stu-id="c0748-155">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="c0748-156">Padrões de constantes</span><span class="sxs-lookup"><span data-stu-id="c0748-156">Constant Patterns</span></span>
<span data-ttu-id="c0748-157">Constantes padrões são numéricos, caracteres e literais de cadeia de caracteres, constantes de enumeração (com o nome de tipo de enumeração incluído).</span><span class="sxs-lookup"><span data-stu-id="c0748-157">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="c0748-158">Um `match` expressão que contém apenas os padrões constantes pode ser comparado a uma instrução case em outros idiomas.</span><span class="sxs-lookup"><span data-stu-id="c0748-158">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="c0748-159">A entrada é comparada com o valor literal e o padrão corresponde se os valores são iguais.</span><span class="sxs-lookup"><span data-stu-id="c0748-159">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="c0748-160">O tipo do literal deve ser compatível com o tipo da entrada.</span><span class="sxs-lookup"><span data-stu-id="c0748-160">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="c0748-161">O exemplo a seguir demonstra o uso de padrões de literais e também usa um padrão de variável e um padrão de OR.</span><span class="sxs-lookup"><span data-stu-id="c0748-161">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="c0748-162">Outro exemplo de um padrão de literal é um padrão com base em constantes de enumeração.</span><span class="sxs-lookup"><span data-stu-id="c0748-162">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="c0748-163">Você deve especificar o nome do tipo de enumeração ao usar constantes de enumeração.</span><span class="sxs-lookup"><span data-stu-id="c0748-163">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="c0748-164">Padrões de identificador</span><span class="sxs-lookup"><span data-stu-id="c0748-164">Identifier Patterns</span></span>
<span data-ttu-id="c0748-165">Se o padrão é uma cadeia de caracteres que constitui um identificador válido, o formato do identificador determina como o padrão é correspondido.</span><span class="sxs-lookup"><span data-stu-id="c0748-165">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="c0748-166">Se o identificador é maior do que um único caractere e começa com um caractere maiusculo, o compilador tenta fazer uma correspondência para o padrão de identificador.</span><span class="sxs-lookup"><span data-stu-id="c0748-166">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="c0748-167">O identificador para esse padrão pode ser um valor marcado com o atributo Literal, um caso de união discriminado, um identificador de exceção ou um caso de padrão ativo.</span><span class="sxs-lookup"><span data-stu-id="c0748-167">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="c0748-168">Se nenhum identificador correspondente for encontrado, a correspondência falhar e a próxima regra padrão, o padrão de variável é comparada com a entrada.</span><span class="sxs-lookup"><span data-stu-id="c0748-168">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="c0748-169">Padrões de união discriminadas podem ser simples denominado casos ou eles podem ter um valor ou uma tupla que contém vários valores.</span><span class="sxs-lookup"><span data-stu-id="c0748-169">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="c0748-170">Se houver um valor, você deve especificar um identificador para o valor.</span><span class="sxs-lookup"><span data-stu-id="c0748-170">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="c0748-171">No caso de uma tupla, você deve fornecer um padrão de tupla com um identificador para cada elemento da tupla ou um identificador com um nome de campo para uma ou mais chamado campos union.</span><span class="sxs-lookup"><span data-stu-id="c0748-171">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="c0748-172">Consulte os exemplos de código nesta seção para obter exemplos.</span><span class="sxs-lookup"><span data-stu-id="c0748-172">See the code examples in this section for examples.</span></span>

<span data-ttu-id="c0748-173">O `option` tipo é uma união discriminada que tem dois casos, `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="c0748-173">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="c0748-174">Um caso (`Some`) tem um valor, mas o outro (`None`) é apenas um caso nomeado.</span><span class="sxs-lookup"><span data-stu-id="c0748-174">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="c0748-175">Portanto, `Some` deve ter uma variável para o valor associado com o `Some` caso, mas `None` deve aparecer sozinho.</span><span class="sxs-lookup"><span data-stu-id="c0748-175">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="c0748-176">No código a seguir, a variável `var1` recebe o valor é obtido por meio da correspondência para o `Some` caso.</span><span class="sxs-lookup"><span data-stu-id="c0748-176">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="c0748-177">No exemplo a seguir, o `PersonName` união discriminada contém uma mistura de cadeias de caracteres e caracteres que representam formas possíveis de nomes.</span><span class="sxs-lookup"><span data-stu-id="c0748-177">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="c0748-178">Os casos de união discriminada são `FirstOnly`, `LastOnly`, e `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="c0748-178">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="c0748-179">Para uniões discriminadas que têm campos nomeados, use o sinal de igual (=) para extrair o valor de um campo.</span><span class="sxs-lookup"><span data-stu-id="c0748-179">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="c0748-180">Por exemplo, considere uma união discriminada com uma declaração semelhante ao seguinte.</span><span class="sxs-lookup"><span data-stu-id="c0748-180">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="c0748-181">Você pode usar os campos nomeados em uma expressão de correspondência de padrão da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="c0748-181">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="c0748-182">O uso do campo nomeado é opcional, portanto, no exemplo anterior, ambos `Circle(r)` e `Circle(radius = r)` têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="c0748-182">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="c0748-183">Quando você especificar vários campos, use o ponto e vírgula (;) como separador.</span><span class="sxs-lookup"><span data-stu-id="c0748-183">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="c0748-184">Padrões ativos permitem definir a correspondência de padrão personalizado mais complexas.</span><span class="sxs-lookup"><span data-stu-id="c0748-184">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="c0748-185">Para obter mais informações sobre padrões ativos, consulte [padrões ativos](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="c0748-185">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="c0748-186">O caso em que o identificador é uma exceção é usado na correspondência de padrão de contexto de manipuladores de exceção.</span><span class="sxs-lookup"><span data-stu-id="c0748-186">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="c0748-187">Para obter informações sobre correspondência de padrão de manipulação de exceção, consulte [exceções: A `try...with` expressão](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c0748-187">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>


## <a name="variable-patterns"></a><span data-ttu-id="c0748-188">Padrões de variáveis</span><span class="sxs-lookup"><span data-stu-id="c0748-188">Variable Patterns</span></span>
<span data-ttu-id="c0748-189">O padrão de variável atribui o valor sendo correspondido a um nome de variável, que estará disponível para uso na expressão à direita da execução de `->` símbolo.</span><span class="sxs-lookup"><span data-stu-id="c0748-189">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="c0748-190">Um padrão de variável sozinho corresponde qualquer entrada, mas padrões variáveis geralmente aparecem em outros padrões, portanto Permitindo estruturas mais complexas, como tuplas e matrizes para ser decomposto em variáveis.</span><span class="sxs-lookup"><span data-stu-id="c0748-190">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="c0748-191">O exemplo a seguir demonstra um padrão de variável dentro de um padrão de tupla.</span><span class="sxs-lookup"><span data-stu-id="c0748-191">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="c0748-192">como padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-192">as Pattern</span></span>
<span data-ttu-id="c0748-193">O `as` padrão é um padrão que tem um `as` cláusula anexada a ele.</span><span class="sxs-lookup"><span data-stu-id="c0748-193">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="c0748-194">O `as` cláusula associa o valor correspondente a um nome que pode ser usado na expressão de execução de um `match` expressão, ou, no caso em que esse padrão é usado em um `let` de associação, o nome é adicionado como uma ligação com o escopo local.</span><span class="sxs-lookup"><span data-stu-id="c0748-194">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="c0748-195">O exemplo a seguir usa um `as` padrão.</span><span class="sxs-lookup"><span data-stu-id="c0748-195">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="c0748-196">OU padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-196">OR Pattern</span></span>
<span data-ttu-id="c0748-197">O padrão ou é usado quando os dados de entrada podem corresponder a vários padrões, e você deseja executar o mesmo código como resultado.</span><span class="sxs-lookup"><span data-stu-id="c0748-197">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="c0748-198">Os tipos de ambos os lados do padrão ou devem ser compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c0748-198">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="c0748-199">O exemplo a seguir demonstra o padrão de OR.</span><span class="sxs-lookup"><span data-stu-id="c0748-199">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="c0748-200">E o padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-200">AND Pattern</span></span>
<span data-ttu-id="c0748-201">O padrão e requer que a entrada corresponder dois padrões.</span><span class="sxs-lookup"><span data-stu-id="c0748-201">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="c0748-202">Os tipos de ambos os lados do padrão e devem ser compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c0748-202">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="c0748-203">O exemplo a seguir é semelhante `detectZeroTuple` mostra o [padrão de tupla](https://msdn.microsoft.com/library/#tuple) seção mais adiante neste tópico, mas aqui ambos `var1` e `var2` são obtidos como valores usando o padrão e.</span><span class="sxs-lookup"><span data-stu-id="c0748-203">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="c0748-204">Contras padrão</span><span class="sxs-lookup"><span data-stu-id="c0748-204">Cons Pattern</span></span>
<span data-ttu-id="c0748-205">O padrão de contras é usado para decompor uma lista para o primeiro elemento, o *head*e uma lista que contém os elementos restantes, o *final*.</span><span class="sxs-lookup"><span data-stu-id="c0748-205">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="c0748-206">Padrão de lista</span><span class="sxs-lookup"><span data-stu-id="c0748-206">List Pattern</span></span>
<span data-ttu-id="c0748-207">O padrão de lista permite que a lista ser decomposto em um número de elementos.</span><span class="sxs-lookup"><span data-stu-id="c0748-207">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="c0748-208">O padrão de lista em si pode corresponder a apenas uma lista de um número específico de elementos.</span><span class="sxs-lookup"><span data-stu-id="c0748-208">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="c0748-209">Padrão de matriz</span><span class="sxs-lookup"><span data-stu-id="c0748-209">Array Pattern</span></span>
<span data-ttu-id="c0748-210">O padrão de matriz é semelhante ao padrão de lista e pode ser usado para decompor as matrizes de um período específico.</span><span class="sxs-lookup"><span data-stu-id="c0748-210">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="c0748-211">Padrão entre parênteses</span><span class="sxs-lookup"><span data-stu-id="c0748-211">Parenthesized Pattern</span></span>
<span data-ttu-id="c0748-212">Parênteses podem ser agrupados em torno de padrões para alcançar a capacidade de associação desejada.</span><span class="sxs-lookup"><span data-stu-id="c0748-212">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="c0748-213">No exemplo a seguir, os parênteses são usados para controlar a associação entre um padrão AND e um padrão de contras.</span><span class="sxs-lookup"><span data-stu-id="c0748-213">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="c0748-214">Padrão de tupla</span><span class="sxs-lookup"><span data-stu-id="c0748-214">Tuple Pattern</span></span>
<span data-ttu-id="c0748-215">O padrão de tupla corresponde a entrada na forma de tupla e permite que a tupla a ser decomposto em seus elementos constituintes usando variáveis para cada posição na tupla de correspondência de padrões.</span><span class="sxs-lookup"><span data-stu-id="c0748-215">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="c0748-216">O exemplo a seguir demonstra o padrão de tupla e também usa padrões literal, padrões de variáveis e o padrão de curinga.</span><span class="sxs-lookup"><span data-stu-id="c0748-216">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="c0748-217">Padrão de registro</span><span class="sxs-lookup"><span data-stu-id="c0748-217">Record Pattern</span></span>
<span data-ttu-id="c0748-218">O padrão de registro é usado para decompor registros para extrair os valores dos campos.</span><span class="sxs-lookup"><span data-stu-id="c0748-218">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="c0748-219">O padrão não precisa fazer referência a todos os campos do registro. todos os campos omitidos apenas não participam de correspondência e não são extraídos.</span><span class="sxs-lookup"><span data-stu-id="c0748-219">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="c0748-220">Padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="c0748-220">Wildcard Pattern</span></span>
<span data-ttu-id="c0748-221">O padrão de curinga é representado por um sublinhado (`_`) de caracteres e corresponde qualquer entrada, assim como o padrão de variável, exceto que a entrada é descartada, em vez de atribuído a uma variável.</span><span class="sxs-lookup"><span data-stu-id="c0748-221">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="c0748-222">O padrão de curinga é geralmente usado em outros padrões como um espaço reservado para valores que não são necessários na expressão à direita do `->` símbolo.</span><span class="sxs-lookup"><span data-stu-id="c0748-222">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="c0748-223">O padrão de curinga é usado frequentemente no final de uma lista de padrões para corresponder a nenhuma entrada não correspondente.</span><span class="sxs-lookup"><span data-stu-id="c0748-223">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="c0748-224">O padrão de curinga é demonstrado em muitos exemplos de código neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c0748-224">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="c0748-225">Consulte o código anterior para obter um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c0748-225">See the preceding code for one example.</span></span>


## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="c0748-226">Padrões com anotações de tipo</span><span class="sxs-lookup"><span data-stu-id="c0748-226">Patterns That Have Type Annotations</span></span>
<span data-ttu-id="c0748-227">Os padrões podem ter anotações de tipo.</span><span class="sxs-lookup"><span data-stu-id="c0748-227">Patterns can have type annotations.</span></span> <span data-ttu-id="c0748-228">Eles se comportam como outras anotações de tipo e guia inferência como outras anotações de tipo.</span><span class="sxs-lookup"><span data-stu-id="c0748-228">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="c0748-229">São necessários parênteses em torno de anotações de tipo em padrões.</span><span class="sxs-lookup"><span data-stu-id="c0748-229">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="c0748-230">O código a seguir mostra um padrão que tem uma anotação de tipo.</span><span class="sxs-lookup"><span data-stu-id="c0748-230">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="c0748-231">Padrão de teste de tipo</span><span class="sxs-lookup"><span data-stu-id="c0748-231">Type Test Pattern</span></span>
<span data-ttu-id="c0748-232">O padrão de teste de tipo é usado para corresponder à entrada em relação a um tipo.</span><span class="sxs-lookup"><span data-stu-id="c0748-232">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="c0748-233">Se o tipo de entrada é uma correspondência (ou um tipo derivado de) o tipo especificado no padrão, a correspondência for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c0748-233">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="c0748-234">O exemplo a seguir demonstra o padrão de teste de tipo.</span><span class="sxs-lookup"><span data-stu-id="c0748-234">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="c0748-235">Padrão nulo</span><span class="sxs-lookup"><span data-stu-id="c0748-235">Null Pattern</span></span>
<span data-ttu-id="c0748-236">O padrão de nulo corresponde o valor nulo que pode aparecer quando você estiver trabalhando com tipos que permitem valor nulo.</span><span class="sxs-lookup"><span data-stu-id="c0748-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="c0748-237">Nulo padrões são usados ao interagir com código do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0748-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="c0748-238">Por exemplo, o valor de retorno de uma API .NET pode ser a entrada para um `match` expressão.</span><span class="sxs-lookup"><span data-stu-id="c0748-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="c0748-239">Você pode controlar o fluxo de programa com base em se o valor de retorno é nulo e também em outras características do valor retornado.</span><span class="sxs-lookup"><span data-stu-id="c0748-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="c0748-240">Você pode usar o padrão de null para impedir que valores nulos sejam propagadas para o restante do seu programa.</span><span class="sxs-lookup"><span data-stu-id="c0748-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="c0748-241">O exemplo a seguir usa o padrão de null e o padrão de variável.</span><span class="sxs-lookup"><span data-stu-id="c0748-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="c0748-242">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c0748-242">See Also</span></span>
[<span data-ttu-id="c0748-243">Expressões Match</span><span class="sxs-lookup"><span data-stu-id="c0748-243">Match Expressions</span></span>](match-expressions.md)

[<span data-ttu-id="c0748-244">Padrões Ativos</span><span class="sxs-lookup"><span data-stu-id="c0748-244">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="c0748-245">Referência da Linguagem F#</span><span class="sxs-lookup"><span data-stu-id="c0748-245">F# Language Reference</span></span>](index.md)