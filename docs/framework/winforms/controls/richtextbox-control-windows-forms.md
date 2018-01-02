---
title: Controle RichTextBox (Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80621a12a4ccd5008a0331af005629d45f60abdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="2cc1a-102">Controle RichTextBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2cc1a-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="2cc1a-103">O controle `RichTextBox` dos Windows Forms é usado para exibir, inserir e manipular texto com formatação.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="2cc1a-104">O `RichTextBox` controle faz tudo o que o <xref:System.Windows.Forms.TextBox> do controle, mas ele também pode exibir fontes, cores e links; carregar texto e imagens inseridas de um arquivo; desfazer e refazer operações; de edição e localizar os caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="2cc1a-105">O controle `RichTextBox` normalmente é usado para fornecer manipulação de texto e exibir recursos semelhantes aos aplicativos de processamento de texto como o Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="2cc1a-106">Como o <xref:System.Windows.Forms.TextBox> controle, o `RichTextBox` controle pode exibir barras de rolagem; mas ao contrário de <xref:System.Windows.Forms.TextBox> controle, exibe barras de rolagem horizontais e verticais por padrão e tem configurações de barra de rolagem adicionais.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cc1a-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2cc1a-107">In This Section</span></span>  
 [<span data-ttu-id="2cc1a-108">Visão geral do controle RichTextBox</span><span class="sxs-lookup"><span data-stu-id="2cc1a-108">RichTextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="2cc1a-109">Apresenta os conceitos gerais do controle `RichTextBox`, que permite aos usuários inserir, exibir e manipular texto com opções de formatação.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="2cc1a-110">Como determinar quando os atributos de formatação mudam no controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-111">Explica como manter o controle de alterações na formatação de fonte e parágrafo no controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="2cc1a-112">Como exibir barras de rolagem no controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-113">Descreve as várias opções disponíveis para barras de rolagem no controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="2cc1a-114">Como exibir links em estilo da Web com o controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-115">Explica como vincular a sites da Web do controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="2cc1a-116">Como habilitar operações do tipo "arrastar e soltar" com o controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-117">Fornece instruções para arrastar os dados no controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="2cc1a-118">Como carregar arquivos no controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-119">Fornece instruções para carregar um arquivo existente para o controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="2cc1a-120">Como salvar arquivos com o controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-121">Fornece instruções para salvar o conteúdo do controle `RichTextBox` em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="2cc1a-122">Como definir atributos de fonte para o controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="2cc1a-123">Descreve como definir a família de fontes, tamanho, estilo e cor do texto no controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="2cc1a-124">Como definir recuos definidos, recuos deslocados e parágrafos com marcadores com o controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="2cc1a-125">Descreve como formatar parágrafos no controle `RichTextBox`.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2cc1a-126">Referência</span><span class="sxs-lookup"><span data-stu-id="2cc1a-126">Reference</span></span>  
 <span data-ttu-id="2cc1a-127">Classe <xref:System.Windows.Forms.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="2cc1a-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="2cc1a-128">Descreve essa classe e tem links para todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2cc1a-129">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="2cc1a-129">Related Sections</span></span>  
 [<span data-ttu-id="2cc1a-130">Controles a serem usados nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cc1a-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="2cc1a-131">Fornece uma lista completa dos controles dos Windows Forms, com links para informações sobre seu uso.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="2cc1a-132">Controle TextBox</span><span class="sxs-lookup"><span data-stu-id="2cc1a-132">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <span data-ttu-id="2cc1a-133">Apresenta os conceitos gerais do <xref:System.Windows.Forms.TextBox> controle, que permite editável, várias linhas de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="2cc1a-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>