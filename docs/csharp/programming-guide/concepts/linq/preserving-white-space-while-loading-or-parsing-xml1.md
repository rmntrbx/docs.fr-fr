---
title: "Conservation des espaces blancs lors du chargement ou de l’analyse de code XML1 | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1b2ec9b5b1bbc343fde5c9527c1e4f4ad7f14796
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Conservation des espaces blancs lors du chargement ou de l’analyse de code XML
Cette rubrique décrit comment contrôler le comportement d'espace blanc de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Un scénario courant consiste à lire le code XML mis en retrait, à créer une arborescence XML en mémoire sans nœuds d'espaces (autrement dit, ne pas conserver les espaces), à effectuer certaines opérations sur le code XML, puis à enregistrer le code XML avec mise en retrait. Lorsque vous sérialisez le code XML avec mise en forme, seuls les espaces significatifs dans l'arborescence XML sont conservés. Il s'agit du comportement par défaut pour [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Un autre scénario courant consiste à lire et à modifier du code XML qui a déjà été intentionnellement mis en retrait. Vous ne souhaiterez peut-être modifier cette mise en retrait en aucune manière. Pour ce faire dans [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], vous devez conserver les espaces lorsque vous chargez ou analysez le code XML et que vous désactivez la mise en forme lors de la sérialisation du code XML.  
  
 Cette rubrique décrit le comportement des espaces blancs des méthodes qui remplissent les arborescences XML. Pour plus d’informations sur le contrôle des espaces blancs quand vous sérialisez des arborescences XML, consultez [Conservation des espaces blancs lors de la sérialisation](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Comportement des méthodes qui remplissent des arborescences XML  
 Les méthodes suivantes des classes <xref:System.Xml.Linq.XElement> et <xref:System.Xml.Linq.XDocument> remplissent une arborescence XML. Vous pouvez remplir une arborescence XML à partir d’un fichier, d’un <xref:System.IO.TextReader>, d’un <xref:System.Xml.XmlReader> ou d’une chaîne :  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 Si la méthode ne prend pas <xref:System.Xml.Linq.LoadOptions> comme argument, elle ne conservera pas les espaces blancs non significatifs.  
  
 Dans la plupart des cas, si la méthode prend <xref:System.Xml.Linq.LoadOptions> comme argument, vous pouvez choisir de conserver les espaces blancs non significatifs sous forme de nœuds de texte dans l’arborescence XML. Toutefois, si la méthode charge le code XML à partir d’un <xref:System.Xml.XmlReader>, c’est le <xref:System.Xml.XmlReader> qui détermine si les espaces blancs sont conservés. La définition de <xref:System.Xml.Linq.LoadOptions> n’a alors pas d’effet.  
  
 Avec ces méthodes, si les espaces blancs sont conservés, des espaces blancs non significatifs sont ajoutés dans l’arborescence XML sous forme de nœuds <xref:System.Xml.Linq.XText>. Si les espaces ne sont pas conservés, aucun nœud de texte n'est inséré.  
  
 Vous pouvez créer une arborescence XML à l’aide d’un <xref:System.Xml.XmlWriter>. L’arborescence est alors remplie avec tous les nœuds écrits dans le <xref:System.Xml.XmlWriter>. Toutefois, lorsque vous générez une arborescence XML à l’aide de cette méthode, tous les nœuds sont conservés, qu’ils soient constitués d’espaces ou non et que ces espaces soient significatifs ou non.  
  
## <a name="see-also"></a>Voir aussi  
 [Analyse de code XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)