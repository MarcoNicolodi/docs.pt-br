---
title: "Enumerações (F#)"
description: "Saiba como usar o F # enumerações em vez de literais para tornar o código mais legível e sustentável."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9272bf5a-9a9f-4314-9e34-a3248e5244f5
ms.openlocfilehash: de0273900b707c99e6fb1bcc84e5c2b9ef2bc725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="enumerations"></a><span data-ttu-id="463e2-104">Enumerações</span><span class="sxs-lookup"><span data-stu-id="463e2-104">Enumerations</span></span>

<span data-ttu-id="463e2-105">*Enumerações*, também conhecido como *enums*, são tipos integrais onde os rótulos são atribuídos a um subconjunto dos valores.</span><span class="sxs-lookup"><span data-stu-id="463e2-105">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="463e2-106">Você pode usá-los no lugar de literais para tornar o código mais legível e fácil de manter.</span><span class="sxs-lookup"><span data-stu-id="463e2-106">You can use them in place of literals to make code more readable and maintainable.</span></span>


## <a name="syntax"></a><span data-ttu-id="463e2-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="463e2-107">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="463e2-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="463e2-108">Remarks</span></span>
<span data-ttu-id="463e2-109">Uma enumeração parece muito, como uma união discriminada que tenha valores simples, exceto que os valores podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="463e2-109">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="463e2-110">Normalmente, os valores são inteiros que começam em 0 ou 1 ou números inteiros que representam as posições de bit.</span><span class="sxs-lookup"><span data-stu-id="463e2-110">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="463e2-111">Se uma enumeração destina-se para representar as posições de bit, você também deve usar o [sinalizadores](xref:System.FlagsAttribute) atributo.</span><span class="sxs-lookup"><span data-stu-id="463e2-111">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="463e2-112">O tipo subjacente da enumeração é determinado de literal que é usada, para que, por exemplo, você pode usar literais com um sufixo, como `1u`, `2u`, e assim por diante, para um inteiro sem sinal (`uint32`) tipo.</span><span class="sxs-lookup"><span data-stu-id="463e2-112">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="463e2-113">Quando você faz referência os valores nomeados, você deve usar o nome do tipo de enumeração em si como um qualificador, ou seja, `enum-name.value1`, não apenas `value1`.</span><span class="sxs-lookup"><span data-stu-id="463e2-113">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="463e2-114">Esse comportamento é diferente do uniões discriminadas.</span><span class="sxs-lookup"><span data-stu-id="463e2-114">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="463e2-115">Isso ocorre porque enumerações sempre têm a [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) atributo.</span><span class="sxs-lookup"><span data-stu-id="463e2-115">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="463e2-116">O código a seguir mostra a declaração e o uso de uma enumeração.</span><span class="sxs-lookup"><span data-stu-id="463e2-116">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="463e2-117">Você pode converter facilmente enumerações para o tipo subjacente usando o operador apropriado, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="463e2-117">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="463e2-118">Tipos enumerados podem ter um dos seguintes tipos de base: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, e `char`.</span><span class="sxs-lookup"><span data-stu-id="463e2-118">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="463e2-119">Tipos de enumeração são representados no .NET Framework, como tipos que são herdados de `System.Enum`, que por sua vez é herdado do `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="463e2-119">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="463e2-120">Portanto, são tipos de valor que estão localizados na pilha ou embutido no objeto que contém, e qualquer valor do tipo subjacente é um valor válido da enumeração.</span><span class="sxs-lookup"><span data-stu-id="463e2-120">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="463e2-121">Isso é significativo quando os valores padrão de correspondência na enumeração, porque você precisa fornecer um padrão que captura os valores sem nome.</span><span class="sxs-lookup"><span data-stu-id="463e2-121">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="463e2-122">O `enum` função na biblioteca F # pode ser usada para gerar um valor de enumeração, até mesmo um valor diferente de predefinida, valores nomeados.</span><span class="sxs-lookup"><span data-stu-id="463e2-122">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="463e2-123">Você usa o `enum` funciona da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="463e2-123">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="463e2-124">O padrão `enum` função funciona com o tipo `int32`.</span><span class="sxs-lookup"><span data-stu-id="463e2-124">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="463e2-125">Portanto, não pode ser usado com tipos de enumeração que têm outros tipos de base.</span><span class="sxs-lookup"><span data-stu-id="463e2-125">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="463e2-126">Em vez disso, use o seguinte.</span><span class="sxs-lookup"><span data-stu-id="463e2-126">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a><span data-ttu-id="463e2-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="463e2-127">See Also</span></span>
[<span data-ttu-id="463e2-128">Referência da Linguagem F#</span><span class="sxs-lookup"><span data-stu-id="463e2-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="463e2-129">Conversões Cast e conversões</span><span class="sxs-lookup"><span data-stu-id="463e2-129">Casting and Conversions</span></span>](casting-and-conversions.md)