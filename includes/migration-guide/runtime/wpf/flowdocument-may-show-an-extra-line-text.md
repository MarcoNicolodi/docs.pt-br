### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="968af-101">FlowDocument pode mostrar uma linha extra de texto</span><span class="sxs-lookup"><span data-stu-id="968af-101">FlowDocument may show an extra line of text</span></span>

|   |   |
|---|---|
|<span data-ttu-id="968af-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="968af-102">Details</span></span>|<span data-ttu-id="968af-103">Em alguns casos, um elemento <xref:System.Windows.Documents.FlowDocument> exibirá uma linha de texto extra ao ser executado no .NET Framework 4.5, em comparação a como ele foi exibido quando executado no .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="968af-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="968af-104">Não conhecemos casos em que a alteração fez com que qualquer texto fosse exibido de forma inadequada ou ilegível, mas textos omitidos de uma exibição de <xref:System.Windows.Documents.FlowDocument> podem aparecer.</span><span class="sxs-lookup"><span data-stu-id="968af-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>|
|<span data-ttu-id="968af-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="968af-105">Suggestion</span></span>|<span data-ttu-id="968af-106">Em alguns casos, diminuir a propriedade PageHeight do elemento de exibição em 1 pode restaurar o número anterior de linhas exibidas.</span><span class="sxs-lookup"><span data-stu-id="968af-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>|
|<span data-ttu-id="968af-107">Escopo</span><span class="sxs-lookup"><span data-stu-id="968af-107">Scope</span></span>|<span data-ttu-id="968af-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="968af-108">Edge</span></span>|
|<span data-ttu-id="968af-109">Versão</span><span class="sxs-lookup"><span data-stu-id="968af-109">Version</span></span>|<span data-ttu-id="968af-110">4.5</span><span class="sxs-lookup"><span data-stu-id="968af-110">4.5</span></span>|
|<span data-ttu-id="968af-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="968af-111">Type</span></span>|<span data-ttu-id="968af-112">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="968af-112">Runtime</span></span>|
|<span data-ttu-id="968af-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="968af-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|
