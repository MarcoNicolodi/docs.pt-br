### <a name="listsort-algorithm-changed"></a><span data-ttu-id="b0e79-101">O algoritmo List.Sort foi alterado</span><span class="sxs-lookup"><span data-stu-id="b0e79-101">List.Sort algorithm changed</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b0e79-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b0e79-102">Details</span></span>|<span data-ttu-id="b0e79-103">A partir do .NET Framework 4.5, o algoritmo de classificação de <xref:System.Collections.Generic.List%601?displayProperty=name> foi alterado (para ser uma classificação introspectiva em vez de uma classificação rápida).</span><span class="sxs-lookup"><span data-stu-id="b0e79-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=name>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="b0e79-104">A classificação de <xref:System.Collections.Generic.List%601?displayProperty=name> nunca foi estável, mas essa alteração pode fazer com que cenários diferentes sejam classificados de maneiras instáveis.</span><span class="sxs-lookup"><span data-stu-id="b0e79-104"><xref:System.Collections.Generic.List%601?displayProperty=name>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="b0e79-105">Isso significa apenas que itens equivalentes podem ser classificados em ordens diferentes em chamadas posteriores da API.</span><span class="sxs-lookup"><span data-stu-id="b0e79-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>|
|<span data-ttu-id="b0e79-106">Sugestão</span><span class="sxs-lookup"><span data-stu-id="b0e79-106">Suggestion</span></span>|<span data-ttu-id="b0e79-107">Como o algoritmo de classificação antigo também era instável (embora de maneiras ligeiramente diferentes), não deve haver nenhum código que dependa de itens equivalentes sempre serem classificados em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="b0e79-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="b0e79-108">Se houver casos de códigos que dependem disso e que tinham sorte com o comportamento antigo, esses códigos deverão ser atualizados para usar um comparador que classifique de forma determinista os itens na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="b0e79-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>|
|<span data-ttu-id="b0e79-109">Escopo</span><span class="sxs-lookup"><span data-stu-id="b0e79-109">Scope</span></span>|<span data-ttu-id="b0e79-110">Transparente</span><span class="sxs-lookup"><span data-stu-id="b0e79-110">Transparent</span></span>|
|<span data-ttu-id="b0e79-111">Versão</span><span class="sxs-lookup"><span data-stu-id="b0e79-111">Version</span></span>|<span data-ttu-id="b0e79-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b0e79-112">4.5</span></span>|
|<span data-ttu-id="b0e79-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0e79-113">Type</span></span>|<span data-ttu-id="b0e79-114">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="b0e79-114">Runtime</span></span>|
|<span data-ttu-id="b0e79-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="b0e79-115">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
