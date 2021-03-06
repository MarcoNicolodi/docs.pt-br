---
title: Visão geral do controle BindingNavigator (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
ms.openlocfilehash: ae1e8273c39122e094817e28379e52c19c573a3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528776"
---
# <a name="bindingnavigator-control-overview-windows-forms"></a>Visão geral do controle BindingNavigator (Windows Forms)
Você pode usar o <xref:System.Windows.Forms.BindingNavigator> controle para criar um meio padronizado para que os usuários de pesquisa e alterar dados em um Windows Form. Você usa com frequência <xref:System.Windows.Forms.BindingNavigator> com o <xref:System.Windows.Forms.BindingSource> componente para permitir que os usuários percorrer os registros de dados em um formulário e interagir com os registros.  
  
## <a name="how-the-bindingnavigator-works"></a>Como o BindingNavigator funciona  
 O <xref:System.Windows.Forms.BindingNavigator> controle é composto de um <xref:System.Windows.Forms.ToolStrip> com uma série de <xref:System.Windows.Forms.ToolStripItem> objetos para a maioria das ações relacionadas a dados comuns: adicionar dados, a exclusão de dados e navegar por dados. Por padrão, o <xref:System.Windows.Forms.BindingNavigator> controle contém esse botões padrão. Captura de tela a seguir mostra o <xref:System.Windows.Forms.BindingNavigator> controle em um formulário.  
  
 ![Controle BindingNavigator](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "cpDataContainerCtrl")  
  
 A tabela a seguir lista os controles e descreve suas funções.  
  
|Controle|Função|  
|-------------|--------------|  
|<xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> botão|Insere uma nova linha na fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> botão|Exclui a linha atual da fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> botão|Move para o primeiro item da fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> botão|Move para o último item da fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> botão|Move para o próximo item da fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> botão|Move para o item anterior da fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> Caixa de texto|Retorna a posição atual na fonte de dados subjacente.|  
|<xref:System.Windows.Forms.BindingNavigator.CountItem%2A> Caixa de texto|Retorna o número total de itens na fonte de dados subjacente.|  
  
 Para cada controle na coleção, existe um membro correspondente do <xref:System.Windows.Forms.BindingSource> componente que fornece a mesma funcionalidade programaticamente. Por exemplo, o <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> botão corresponde à <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> método do <xref:System.Windows.Forms.BindingSource> componente, o <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> botão corresponde à <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> método e assim por diante.  
  
 Se os botões padrão não são adequados para seu aplicativo, ou se você precisar de botões adicionais para dar suporte a outros tipos de funcionalidade, você pode fornecer sua própria <xref:System.Windows.Forms.ToolStrip> botões. Consulte também [Como adicionar botões Carregar, Salvar e Cancelar ao controle BindingNavigator do Windows Forms](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 [Controle BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
