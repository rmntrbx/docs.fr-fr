---
title: "Non conforme à CLS &lt;membername&gt; n’est pas autorisé dans une interface conforme CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74744b89ad72b6fd051f83ba38354d0a277555c8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Non conforme à CLS &lt;membername&gt; n’est pas autorisé dans une interface conforme CLS
Une propriété, une procédure ou un événement dans une interface est marquée en tant que `<CLSCompliant(True)>` lorsque l’interface elle-même est marqué comme `<CLSCompliant(False)>` ou n’est pas marqué.  
  
 Pour une interface soit conforme à la [indépendance du langage et composants indépendants du langage](../../../standard/language-independence-and-language-independent-components.md) (CLS), tous ses membres doivent être conformes.  
  
 Quand vous appliquez l’attribut <xref:System.CLSCompliantAttribute> à un élément de programmation, vous affectez au paramètre `isCompliant` de l’attribut la valeur `True` ou `False` pour indiquer la conformité ou la non-conformité. Il n’existe pas de valeur par défaut pour ce paramètre et vous devez fournir une valeur.  
  
 Si vous n’appliquez pas <xref:System.CLSCompliantAttribute> à un élément, il est considéré comme étant non conforme.  
  
 Par défaut, ce message est un avertissement. Pour plus d’informations sur le masquage des avertissements ou leur traitement en tant qu’erreurs, consultez [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID d’erreur :** BC40033  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Si vous avez besoin de la conformité CLS et que vous contrôlez le code source de l’interface, marquez l’interface comme `<CLSCompliant(True)>` si tous ses membres sont conformes.  
  
-   Si vous la conformité CLS et que vous n’avez pas de contrôle du code de l’interface source, ou si elle ne peut pas être conforme, définissez ce membre dans une autre interface.  
  
-   Si vous avez besoin que ce membre doit rester dans son interface actuelle, supprimez le <xref:System.CLSCompliantAttribute> à partir de sa définition ou marquez-le comme `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface (instruction)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 
