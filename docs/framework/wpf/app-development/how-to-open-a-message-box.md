---
title: "Comment : ouvrir une boîte de Message"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1754fa190a638c1a200805e339f91bd582d27c4c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-message-box"></a>Comment : ouvrir une boîte de Message
Cet exemple montre comment ouvrir une boîte de message.  
  
## <a name="example"></a>Exemple  
 Une boîte de message est une boîte de dialogue modale préfabriquée pour afficher des informations pour les utilisateurs. Une boîte de message est ouverte en appelant la méthode statique <xref:System.Windows.MessageBox.Show%2A> méthode de la <xref:System.Windows.MessageBox> classe. Lorsque <xref:System.Windows.MessageBox.Show%2A> est appelée, le message est transmis à l’aide d’un paramètre de chaîne. Plusieurs surcharges de <xref:System.Windows.MessageBox.Show%2A> vous permettent de configurer l’apparence d’une boîte de message (voir <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Voir aussi  
 [MessageBox, exemple](http://go.microsoft.com/fwlink/?LinkID=160023)
