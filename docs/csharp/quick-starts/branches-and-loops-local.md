---
title: "Início rápido - Branches e loops - Guia de C#"
description: "Neste início rápido sobre branches e loops, você escreve código em C# para explorar a sintaxe de linguagem que dá suporte a branches e loops condicionais para execução repetida de instruções."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 7954475616b122f8bb96ad00d05b476b3beeb52c
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="branches-and-loops"></a><span data-ttu-id="b7c19-103">Loops e branches</span><span class="sxs-lookup"><span data-stu-id="b7c19-103">Branches and loops</span></span>

<span data-ttu-id="b7c19-104">Este início rápido ensina a escrever códigos que examinam variáveis e mudam o caminho de execução com base nessas variáveis.</span><span class="sxs-lookup"><span data-stu-id="b7c19-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="b7c19-105">Escreva o código em C# e veja os resultados da compilação e da execução.</span><span class="sxs-lookup"><span data-stu-id="b7c19-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="b7c19-106">O início rápido contém uma série de lições que exploram construções de ramificação e loop em C#.</span><span class="sxs-lookup"><span data-stu-id="b7c19-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="b7c19-107">Estas lições ensinam os princípios básicos da linguagem C#.</span><span class="sxs-lookup"><span data-stu-id="b7c19-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="b7c19-108">Este início rápido espera que você tenha uma máquina que possa usar para desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="b7c19-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="b7c19-109">O tópico do .NET [Familiarize-se em 10 minutos](https://www.microsoft.com/net/core) tem instruções para configurar o ambiente de desenvolvimento local no Mac, PC ou Linux.</span><span class="sxs-lookup"><span data-stu-id="b7c19-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="b7c19-110">Confira uma visão geral dos comandos que você usará na [introdução aos inícios rápidos locais](local-environment.md) com links para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b7c19-110">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="b7c19-111">Tome decisões usando a instrução `if`</span><span class="sxs-lookup"><span data-stu-id="b7c19-111">Make decisions using the `if` statement</span></span>

<span data-ttu-id="b7c19-112">Crie um diretório chamado **branches-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="b7c19-112">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="b7c19-113">Torne-o o diretório atual e execute `dotnet new console -n BranchesAndLoops -o .`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-113">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="b7c19-114">Esse comando cria um novo aplicativo de console .NET Core no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="b7c19-114">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="b7c19-115">Abra **Program.cs** em seu editor favorito e substitua a linha `Console.Writeline("Hello World!");` pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="b7c19-115">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="b7c19-116">Tente este código digitando `dotnet run` na janela de seu console.</span><span class="sxs-lookup"><span data-stu-id="b7c19-116">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="b7c19-117">Você deve ver a mensagem "A resposta é maior do que 10."</span><span class="sxs-lookup"><span data-stu-id="b7c19-117">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="b7c19-118">impressa no console.</span><span class="sxs-lookup"><span data-stu-id="b7c19-118">printed to your console.</span></span>

<span data-ttu-id="b7c19-119">Modifique a declaração de `b` para que a soma seja inferior a 10:</span><span class="sxs-lookup"><span data-stu-id="b7c19-119">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="b7c19-120">Digite `dotnet run` novamente.</span><span class="sxs-lookup"><span data-stu-id="b7c19-120">Type `dotnet run` again.</span></span> <span data-ttu-id="b7c19-121">Como a resposta é inferior a 10, nada é impresso.</span><span class="sxs-lookup"><span data-stu-id="b7c19-121">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="b7c19-122">A **condição** que você está testando é falsa.</span><span class="sxs-lookup"><span data-stu-id="b7c19-122">The **condition** you're testing is false.</span></span> <span data-ttu-id="b7c19-123">Não há qualquer código para execução, porque você escreveu apenas uma das ramificações possíveis para uma instrução `if`: a ramificação verdadeira.</span><span class="sxs-lookup"><span data-stu-id="b7c19-123">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="b7c19-124">À medida que explora C# (ou qualquer linguagem de programação), você cometerá erros ao escrever o código.</span><span class="sxs-lookup"><span data-stu-id="b7c19-124">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="b7c19-125">O compilador encontrará e reportará esses erros.</span><span class="sxs-lookup"><span data-stu-id="b7c19-125">The compiler will find and report the errors.</span></span> <span data-ttu-id="b7c19-126">Verifique atentamente a saída do erro e o código que gerou o erro.</span><span class="sxs-lookup"><span data-stu-id="b7c19-126">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="b7c19-127">Normalmente, o erro do compilador pode ajudar você a localizar o problema.</span><span class="sxs-lookup"><span data-stu-id="b7c19-127">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="b7c19-128">Este primeiro exemplo mostra o poder dos tipos `if` e Booliano.</span><span class="sxs-lookup"><span data-stu-id="b7c19-128">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="b7c19-129">Um *Booliano* é uma variável que pode ter um dos dois valores: `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-129">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="b7c19-130">C# define um tipo especial, `bool` para variáveis Boolianas.</span><span class="sxs-lookup"><span data-stu-id="b7c19-130">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="b7c19-131">A instrução `if` verifica o valor de um `bool`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-131">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="b7c19-132">Quando o valor é `true`, a instrução após `if` é executada.</span><span class="sxs-lookup"><span data-stu-id="b7c19-132">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="b7c19-133">Caso contrário, é ignorada.</span><span class="sxs-lookup"><span data-stu-id="b7c19-133">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="b7c19-134">Esse processo de verificação de condições e execução de instruções com base nessas condições é muito eficiente.</span><span class="sxs-lookup"><span data-stu-id="b7c19-134">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="b7c19-135">Faça if e else funcionam juntas</span><span class="sxs-lookup"><span data-stu-id="b7c19-135">Make if and else work together</span></span>

<span data-ttu-id="b7c19-136">Para executar um código diferente nos branches true e false, crie um branch `else` que será executado quando a condição for false.</span><span class="sxs-lookup"><span data-stu-id="b7c19-136">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="b7c19-137">Experimente isto.</span><span class="sxs-lookup"><span data-stu-id="b7c19-137">Try this.</span></span> <span data-ttu-id="b7c19-138">Adicione as duas últimas linhas do código abaixo ao seu método `Main` (você já deve ter os quatro primeiros):</span><span class="sxs-lookup"><span data-stu-id="b7c19-138">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="b7c19-139">A instrução após a palavra-chave `else` é executada somente quando a condição que estiver sendo testada for `false`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-139">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="b7c19-140">A combinação de `if` e `else` com condições Boolianas fornece todos os recursos que você precisa para lidar com uma condição `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-140">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7c19-141">O recuo sob as instruções `if` e `else` é para leitores humanos.</span><span class="sxs-lookup"><span data-stu-id="b7c19-141">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="b7c19-142">A linguagem C# não considera recuo ou espaço em branco como significativo.</span><span class="sxs-lookup"><span data-stu-id="b7c19-142">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="b7c19-143">A instrução após a palavra-chave `if` ou `else` será executada com base na condição.</span><span class="sxs-lookup"><span data-stu-id="b7c19-143">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="b7c19-144">Todos os exemplos neste início rápido seguem uma prática comum para recuar linhas com base no fluxo de controle de instruções.</span><span class="sxs-lookup"><span data-stu-id="b7c19-144">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="b7c19-145">Como o recuo não é significativo, você precisa usar `{` e `}` para indicar quando você quer que mais de uma instrução faça parte do bloco executado condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="b7c19-145">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="b7c19-146">Os programadores em C# normalmente usam essas chaves em todas as cláusulas `if` e `else`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-146">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="b7c19-147">O exemplo a seguir é igual ao que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="b7c19-147">The following example is the same as the one you just created.</span></span> <span data-ttu-id="b7c19-148">Modifique o código acima para coincidir com o código a seguir:</span><span class="sxs-lookup"><span data-stu-id="b7c19-148">Modify your code above to match the following code:</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> <span data-ttu-id="b7c19-149">No restante deste início rápido, todos os exemplos de código incluem as chaves, seguindo as práticas aceitas.</span><span class="sxs-lookup"><span data-stu-id="b7c19-149">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="b7c19-150">Você pode testar condições mais complicadas.</span><span class="sxs-lookup"><span data-stu-id="b7c19-150">You can test more complicated conditions.</span></span> <span data-ttu-id="b7c19-151">Adicione o seguinte código ao seu método `Main` após o código que você escreveu até agora:</span><span class="sxs-lookup"><span data-stu-id="b7c19-151">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

<span data-ttu-id="b7c19-152">O `&&` representa "e".</span><span class="sxs-lookup"><span data-stu-id="b7c19-152">The `&&` represents "and".</span></span> <span data-ttu-id="b7c19-153">Isso significa que as duas condições devem ser verdadeiras para executar a instrução no branch verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="b7c19-153">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="b7c19-154">Estes exemplos também mostram que você pode ter várias instruções em cada branch condicional, desde que você coloque-as entre `{` e `}`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-154">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="b7c19-155">Você também pode usar `||` para representar "ou".</span><span class="sxs-lookup"><span data-stu-id="b7c19-155">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="b7c19-156">Adicione o código a seguir após o que você escreveu até o momento:</span><span class="sxs-lookup"><span data-stu-id="b7c19-156">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

<span data-ttu-id="b7c19-157">Você terminou a primeira etapa.</span><span class="sxs-lookup"><span data-stu-id="b7c19-157">You've finished the first step.</span></span> <span data-ttu-id="b7c19-158">Antes de iniciar a próxima seção, vamos passar o código atual para um método separado.</span><span class="sxs-lookup"><span data-stu-id="b7c19-158">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="b7c19-159">Isso facilita o começo do trabalho com um exemplo novo.</span><span class="sxs-lookup"><span data-stu-id="b7c19-159">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="b7c19-160">Renomeie seu método `Main` como `ExploreIf` e escreva um novo método `Main` que chama `ExploreIf`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-160">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="b7c19-161">Quando você terminar, seu código deverá parecer com isto:</span><span class="sxs-lookup"><span data-stu-id="b7c19-161">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

<span data-ttu-id="b7c19-162">Comente a chamada para `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-162">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="b7c19-163">Isso tornará a saída menos congestionada enquanto você trabalha nesta seção:</span><span class="sxs-lookup"><span data-stu-id="b7c19-163">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="b7c19-164">O `//` inicia um **comentário** em C#.</span><span class="sxs-lookup"><span data-stu-id="b7c19-164">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="b7c19-165">Os comentários são qualquer texto que você queira manter em seu código-fonte, mas não queria executar como código.</span><span class="sxs-lookup"><span data-stu-id="b7c19-165">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="b7c19-166">O compilador não gera qualquer código executável a partir dos comentários.</span><span class="sxs-lookup"><span data-stu-id="b7c19-166">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="b7c19-167">Use loops para repetir operações</span><span class="sxs-lookup"><span data-stu-id="b7c19-167">Use loops to repeat operations</span></span>

<span data-ttu-id="b7c19-168">Nesta seção, você usa **loops** repetir as instruções.</span><span class="sxs-lookup"><span data-stu-id="b7c19-168">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="b7c19-169">Tente este código em seu método `Main`:</span><span class="sxs-lookup"><span data-stu-id="b7c19-169">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="b7c19-170">A instrução `while` verifica uma condição e executa a instrução, ou bloco de instruções, após o `while`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-170">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="b7c19-171">Ela verifica repetidamente a condição e executa essas instruções até que a condição seja falsa.</span><span class="sxs-lookup"><span data-stu-id="b7c19-171">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="b7c19-172">Há outro operador novo neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b7c19-172">There's one other new operator in this example.</span></span> <span data-ttu-id="b7c19-173">O `++` após a variável `counter` é o operador **increment**.</span><span class="sxs-lookup"><span data-stu-id="b7c19-173">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="b7c19-174">Ele adiciona 1 ao valor de `counter` e armazena esse valor na variável `counter`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-174">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7c19-175">Verifique se a condição de loop `while` muda para false ao executar o código.</span><span class="sxs-lookup"><span data-stu-id="b7c19-175">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="b7c19-176">Caso contrário, crie um **loop infinito**, para que seu programa nunca termine.</span><span class="sxs-lookup"><span data-stu-id="b7c19-176">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="b7c19-177">Isso não é demonstrado neste exemplo, porque você tem que forçar o programa a encerrar usando **CTRL-C** ou outros meios.</span><span class="sxs-lookup"><span data-stu-id="b7c19-177">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="b7c19-178">O loop `while` testa a condição antes de executar o código seguindo `while`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-178">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="b7c19-179">O loop `do` ... `while` executa o código primeiro e, em seguida, verifica a condição.</span><span class="sxs-lookup"><span data-stu-id="b7c19-179">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="b7c19-180">O loop do while é mostrado no código a seguir:</span><span class="sxs-lookup"><span data-stu-id="b7c19-180">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="b7c19-181">Esse loop `do` e o loop `while` anterior produzem a mesma saída.</span><span class="sxs-lookup"><span data-stu-id="b7c19-181">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="b7c19-182">Trabalhar com o loop for</span><span class="sxs-lookup"><span data-stu-id="b7c19-182">Work with the for loop</span></span>

<span data-ttu-id="b7c19-183">O loop **for** é usado normalmente em C#.</span><span class="sxs-lookup"><span data-stu-id="b7c19-183">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="b7c19-184">Tente este código em seu método Main():</span><span class="sxs-lookup"><span data-stu-id="b7c19-184">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="b7c19-185">Ele faz o mesmo trabalho que o loop `while` e o loop `do` que você já usou.</span><span class="sxs-lookup"><span data-stu-id="b7c19-185">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="b7c19-186">A instrução `for` tem três partes que controlam o modo como ela funciona.</span><span class="sxs-lookup"><span data-stu-id="b7c19-186">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="b7c19-187">A primeira parte é o **inicializador for**: `for index = 0;` declara que `index` é a variável do loop, e define seu valor inicial como `0`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-187">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="b7c19-188">A parte central é a **condição for**: `index < 10` declara que este loop `for` continuará sendo executado desde que o valor do contador seja inferior a 10.</span><span class="sxs-lookup"><span data-stu-id="b7c19-188">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="b7c19-189">A parte final é o **iterador for**: `index++` especifica como modificar a variável de loop depois de executar o bloco após a instrução `for`.</span><span class="sxs-lookup"><span data-stu-id="b7c19-189">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="b7c19-190">Aqui, ela especifica que `index` deve ser incrementado com 1 sempre que o bloco for executado.</span><span class="sxs-lookup"><span data-stu-id="b7c19-190">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="b7c19-191">Experimente você mesmo.</span><span class="sxs-lookup"><span data-stu-id="b7c19-191">Experiment with these yourself.</span></span> <span data-ttu-id="b7c19-192">Tente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b7c19-192">Try each of the following:</span></span>

- <span data-ttu-id="b7c19-193">Altere o inicializador para iniciar em um valor diferente.</span><span class="sxs-lookup"><span data-stu-id="b7c19-193">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="b7c19-194">Altere a condição para parar em um valor diferente.</span><span class="sxs-lookup"><span data-stu-id="b7c19-194">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="b7c19-195">Quando terminar, vamos escrever um código para usar o que você aprendeu.</span><span class="sxs-lookup"><span data-stu-id="b7c19-195">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="b7c19-196">Combinar branches e loops</span><span class="sxs-lookup"><span data-stu-id="b7c19-196">Combine branches and loops</span></span>

<span data-ttu-id="b7c19-197">Agora que você viu a instrução `if` e as construções de loop na linguagem C#, verifique se você pode escrever o código C# para encontrar a soma de todos os inteiros de 1 a 20 divisíveis por 3.</span><span class="sxs-lookup"><span data-stu-id="b7c19-197">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="b7c19-198">Veja algumas dicas:</span><span class="sxs-lookup"><span data-stu-id="b7c19-198">Here are a few hints:</span></span>

- <span data-ttu-id="b7c19-199">O operador `%` retorna o restante de uma operação de divisão.</span><span class="sxs-lookup"><span data-stu-id="b7c19-199">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="b7c19-200">A instrução `if` retorna a condição para ver se um número deve ser parte da soma.</span><span class="sxs-lookup"><span data-stu-id="b7c19-200">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="b7c19-201">O loop `for` pode ajudar você a repetir uma série de etapas para todos os números de 1 a 20.</span><span class="sxs-lookup"><span data-stu-id="b7c19-201">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="b7c19-202">Tente você mesmo.</span><span class="sxs-lookup"><span data-stu-id="b7c19-202">Try it yourself.</span></span> <span data-ttu-id="b7c19-203">Depois verifique como você fez.</span><span class="sxs-lookup"><span data-stu-id="b7c19-203">Then check how you did.</span></span> <span data-ttu-id="b7c19-204">Você deve obter 63 como resposta.</span><span class="sxs-lookup"><span data-stu-id="b7c19-204">You should get 63 for an answer.</span></span> <span data-ttu-id="b7c19-205">Veja uma resposta possível [exibindo o código completo no GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="b7c19-205">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="b7c19-206">Você concluiu o início rápido "branches e loops".</span><span class="sxs-lookup"><span data-stu-id="b7c19-206">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="b7c19-207">Continue com o início rápido [Matrizes e coleções](arrays-and-collections.md) em seu próprio ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="b7c19-207">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="b7c19-208">Saiba mais sobre esses conceitos nestes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b7c19-208">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="b7c19-209">[Instrução If e else](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="b7c19-209">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="b7c19-210">[Instrução while](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="b7c19-210">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="b7c19-211">[Instrução Do](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="b7c19-211">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="b7c19-212">Instrução for</span><span class="sxs-lookup"><span data-stu-id="b7c19-212">For statement</span></span>](../language-reference/keywords/for.md)   