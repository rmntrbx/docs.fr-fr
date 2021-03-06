---
title: "Comment : charger du code XML à partir d'un fichier, d'une chaîne ou d'un flux (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 572e34b1cd4813fad35e6afaf2ec3d0d9dac470a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Comment : charger du code XML à partir d'un fichier, d'une chaîne ou d'un flux (Visual Basic)
Vous pouvez créer [littéraux XML](../../../../visual-basic/language-reference/xml-literals/index.md) et les remplir avec le contenu à partir d’une source externe, comme un fichier, une chaîne ou un flux de données à l’aide de plusieurs méthodes. Ces méthodes sont illustrées dans les exemples suivants.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Charger XML à partir d’un fichier  
  
-   Pour remplir un littéral XML tel qu’un <xref:System.Xml.Linq.XElement> ou <xref:System.Xml.Linq.XDocument> objet à partir d’un fichier, utilisez le `Load` (méthode). Cette méthode peut prendre un chemin d’accès du fichier, un flux de texte ou un flux XML comme entrée.  
  
     L’exemple de code suivant illustre l’utilisation de la <xref:System.Xml.Linq.XDocument.Load%28System.String%29> méthode pour remplir un <xref:System.Xml.Linq.XDocument> objet avec les données XML à partir d’un fichier texte.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Charger XML à partir d’une chaîne  
  
-   Pour remplir un littéral XML tel qu’un <xref:System.Xml.Linq.XElement> ou <xref:System.Xml.Linq.XDocument> de l’objet d’une chaîne, vous pouvez utiliser la `Parse` (méthode).  
  
     L’exemple de code suivant illustre l’utilisation de la <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> méthode pour remplir un <xref:System.Xml.Linq.XDocument> objet XML à partir d’une chaîne.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Charger XML à partir d’un flux de données  
  
-   Pour remplir un littéral XML tel qu’un <xref:System.Xml.Linq.XElement> ou <xref:System.Xml.Linq.XDocument> de l’objet à partir d’un flux de données, vous pouvez utiliser la `Load` méthode ou la <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> (méthode).  
  
 L’exemple de code suivant illustre l’utilisation de la <xref:System.Xml.Linq.XNode.ReadFrom%2A> méthode pour remplir un <xref:System.Xml.Linq.XDocument> objet avec les données XML à partir d’un flux XML.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [Littéraux XML](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Manipulation de code XML dans Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
