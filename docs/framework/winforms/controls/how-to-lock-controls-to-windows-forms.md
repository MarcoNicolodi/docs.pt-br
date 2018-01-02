---
title: Como bloquear controles nos Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30808d2102a1be41381f0e07c9f0f37bfb4a5a56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="c92ea-102">Como bloquear controles nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c92ea-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="c92ea-103">Ao projetar a interface do usuário do seu aplicativo do Windows, você pode bloquear os controles quando eles são posicionados corretamente, para que você não os mova nem os redimensione inadvertidamente ao configurar outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="c92ea-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="c92ea-104">Além disso, você pode bloquear e desbloquear todos os controles no formulário de uma vez, o que é útil para formulários com muitos controles ou você pode desbloquear controles individuais.</span><span class="sxs-lookup"><span data-stu-id="c92ea-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="c92ea-105">Depois de colocar todos os controles no local desejado no formulário, bloqueie-os no local para evitar a movimentação incorreta.</span><span class="sxs-lookup"><span data-stu-id="c92ea-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c92ea-106">As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas.</span><span class="sxs-lookup"><span data-stu-id="c92ea-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c92ea-107">Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="c92ea-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c92ea-108">Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c92ea-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="c92ea-109">Para bloquear um controle</span><span class="sxs-lookup"><span data-stu-id="c92ea-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="c92ea-110">Na janela **Propriedades**, clique na propriedade **Bloqueado** e selecione `true`.</span><span class="sxs-lookup"><span data-stu-id="c92ea-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="c92ea-111">(Clicar duas vezes no nome alterna a configuração da propriedade.)</span><span class="sxs-lookup"><span data-stu-id="c92ea-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="c92ea-112">Como alternativa, clique com o botão direito do mouse no controle e escolha **Bloquear Controles**.</span><span class="sxs-lookup"><span data-stu-id="c92ea-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c92ea-113">O bloqueio dos controles evita que eles sejam arrastados para um novo tamanho ou local na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c92ea-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="c92ea-114">No entanto, você ainda pode alterar o tamanho ou local dos controles por meio da janela **Propriedades** ou no código.</span><span class="sxs-lookup"><span data-stu-id="c92ea-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="c92ea-115">Para bloquear todos os controles em um formulário</span><span class="sxs-lookup"><span data-stu-id="c92ea-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="c92ea-116">No menu **Formatar**, escolha **Bloquear Controles**.</span><span class="sxs-lookup"><span data-stu-id="c92ea-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c92ea-117">Esse comando bloqueia também o tamanho do formulário, pois um formulário é um controle.</span><span class="sxs-lookup"><span data-stu-id="c92ea-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="c92ea-118">Para desbloquear todos os controles bloqueados em um formulário</span><span class="sxs-lookup"><span data-stu-id="c92ea-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="c92ea-119">No menu **Formatar**, escolha **Bloquear Controles**.</span><span class="sxs-lookup"><span data-stu-id="c92ea-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="c92ea-120">Todos os controles bloqueados anteriormente no formulário agora estão desbloqueados.</span><span class="sxs-lookup"><span data-stu-id="c92ea-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="c92ea-121">Para desbloquear controles bloqueados individualmente</span><span class="sxs-lookup"><span data-stu-id="c92ea-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="c92ea-122">Na janela **Propriedades**, clique na propriedade **Bloqueado** e selecione `false`.</span><span class="sxs-lookup"><span data-stu-id="c92ea-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="c92ea-123">(Clicar duas vezes no nome alterna a configuração da propriedade.)</span><span class="sxs-lookup"><span data-stu-id="c92ea-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92ea-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c92ea-124">See Also</span></span>  
 [<span data-ttu-id="c92ea-125">Controles dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c92ea-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="c92ea-126">Organizando Controles nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c92ea-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="c92ea-127">Rotulando controles individuais dos Windows Forms e fornecendo atalhos para eles</span><span class="sxs-lookup"><span data-stu-id="c92ea-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="c92ea-128">Controles a serem usados nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c92ea-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="c92ea-129">Controles dos Windows Forms por função</span><span class="sxs-lookup"><span data-stu-id="c92ea-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)