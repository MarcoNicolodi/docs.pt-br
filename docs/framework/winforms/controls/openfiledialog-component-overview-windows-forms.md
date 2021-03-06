---
title: Visão geral do componente OpenFileDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: a49298b2e2cc620ad95e2e0b601a2f49f6ff79d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536072"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Visão geral do componente OpenFileDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.OpenFileDialog> componente é uma caixa de diálogo pré-configurado. É a mesma caixa de diálogo **Abrir arquivo** exposta pelo sistema operacional Windows. Ele herda o <xref:System.Windows.Forms.CommonDialog> classe.  
  
## <a name="using-this-component"></a>Usando este componente  
 Use esse componente em seu aplicativo baseado no Windows como uma solução simples para seleção de arquivos em vez de configurar sua própria caixa de diálogo. Com base nas caixas de diálogo padrão do Windows, crie aplicativos cuja funcionalidade básica é imediatamente familiar aos usuários. Lembre-se, no entanto, que, quando usar o <xref:System.Windows.Forms.OpenFileDialog> componente, você deve escrever sua própria lógica de abertura de arquivo.  
  
 Use o <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para exibir a caixa de diálogo em tempo de execução. Você pode habilitar os usuários para selecionar vários arquivos a serem abertos com o <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> propriedade. Além disso, você pode usar o <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> propriedade para determinar se uma caixa de seleção de somente leitura é exibido na caixa de diálogo. O <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> propriedade indica se a caixa de seleção de somente leitura está selecionada. Por fim, o <xref:System.Windows.Forms.FileDialog.Filter%2A> propriedade define a atual arquivo nome cadeia de filtro, que determina as opções que aparecem na caixa "Arquivos do tipo" na caixa de diálogo.  
  
 Quando ele é adicionado a um formulário, o <xref:System.Windows.Forms.OpenFileDialog> componente aparece na bandeja de na parte inferior do Designer de formulários do Windows.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [Componente OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
