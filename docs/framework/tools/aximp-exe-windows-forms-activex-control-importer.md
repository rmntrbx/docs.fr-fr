---
title: "Aximp.exe (Windows Forms ActiveX Control Importer) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "ActiveX controls, hosting in Windows Forms"
  - "ActiveX Control Importer"
  - "type definitions, converting"
  - "Aximp.exe"
  - "Windows Forms ActiveX Control Importer"
ms.assetid: 482c0d83-7144-4497-b626-87d2351b78d0
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Aximp.exe (Windows Forms ActiveX Control Importer)
L'importateur de contrôles ActiveX convertit les définitions de types d'une bibliothèque de types COM associées à un contrôle ActiveX en un contrôle Windows Forms.  
  
 Windows Forms peut héberger uniquement des contrôles Windows Forms, c'est\-à\-dire, des classes dérivées de <xref:System.Windows.Forms.Control>.  Aximp.exe génère une classe wrapper associée à un contrôle ActiveX qui peut être hébergée dans un Windows Form.  Cela vous permet d'utiliser la même prise en charge au moment du design et la même méthodologie de programmation que pour d'autres contrôles Windows Forms.  
  
 Pour héberger le contrôle ActiveX, vous devez générer un contrôle wrapper qui dérive de <xref:System.Windows.Forms.AxHost>.  Ce contrôle wrapper contient une instance du contrôle ActiveX sous\-jacent.  Il sait comment communiquer avec le contrôle ActiveX, mais il se présente comme un contrôle Windows Forms.  Le contrôle ainsi généré héberge le contrôle ActiveX dont il expose les propriétés, les méthodes et les événements comme si ces derniers lui appartenaient.  
  
 Cet outil est installé automatiquement avec Visual Studio.  Pour exécuter l'outil, utilisez l'invite de commandes développeur \(ou l'invite de commandes Visual Studio dans Windows 7\).  Pour plus d'informations, consultez [Invites de commandes](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 À l'invite de commandes, tapez le texte suivant :  
  
## Syntaxe  
  
```  
aximp [options]{file.dll | file.ocx}  
```  
  
## Notes  
  
|Argument|Description|  
|--------------|-----------------|  
|*file*|Nom du fichier source contenant le contrôle ActiveX à convertir.  La valeur de cet argument doit présenter l'extension .dll ou .ocx.|  
  
|Option|Description|  
|------------|-----------------|  
|`/delaysign`|Spécifie à Aximp.exe que le contrôle résultant doit être signé à l'aide du processus de signature différée.  Vous devez spécifier cette option avec l'option `/keycontainer:`, `/keyfile:` ou `/publickey:`.  Pour plus d'informations sur le processus de signature différée, consultez [Temporisation de signature d'un assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).|  
|`/help`|Affiche la syntaxe et les options de commande de l'outil.|  
|`/keycontainer:` *containerName*|Signe le contrôle résultant avec un nom fort en utilisant la paire de clés publique\/privée présente dans le conteneur de clé spécifié par *containerName*.|  
|`/keyfile:` *filename*|Signe le contrôle résultant avec un nom fort en utilisant la paire de clés publique\/privée officielle de l'éditeur présente dans *filename*.|  
|`/nologo`|Supprime l'affichage de la bannière de démarrage Microsoft.|  
|`/out:` *filename*|Spécifie le nom de l'assembly à créer.|  
|`/publickey:` *filename*|Signe le contrôle résultant avec un nom fort à l'aide de la clé publique présente dans le fichier spécifié par *filename*.|  
|`/rcw:` *filename*|Utilise le wrapper RCW spécifié plutôt que d'en générer un nouveau.  Vous pouvez spécifier plusieurs instances.  Le répertoire actif est utilisé pour les chemins d'accès relatifs.  Pour plus d'informations, consultez [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md).|  
|`/silent`|Supprime l'affichage des messages indiquant la réussite des opérations.|  
|`/source`|Génère le code source C\# pour le wrapper Windows Forms.|  
|`/verbose`|Spécifie le mode Commentaires ; affiche des informations supplémentaires sur la progression de l'opération.|  
|`/?`|Affiche la syntaxe et les options de commande de l'outil.|  
  
 Aximp.exe convertit toute une bibliothèque de types de contrôles ActiveX à la fois et produit un ensemble d'assemblys contenant les métadonnées du Common Language Runtime et l'implémentation des contrôles pour les types définis dans la bibliothèque de types d'origines.  Les fichiers générés sont nommés conformément à la règle suivante :  
  
 Proxy du Common Language Runtime pour les types COM : *progid*.dll  
  
 Proxy Windows Forms pour les contrôles ActiveX \(où Ax est l'abréviation de ActiveX\) : Ax*progid*.dll  
  
> [!NOTE]
>  Si le nom d'un membre du contrôle ActiveX correspond à un nom défini dans le .NET Framework, Aximp.exe fait précéder le nom du membre avec « Ctl » lorsqu'il crée la classe dérivée AxHost.  Par exemple, si votre contrôle ActiveX possède un membre nommé "Layout", il est renommé "CtlLayout" dans la classe dérivée AxHost, car l'événement Layout est défini dans le .NET Framework.  
  
 Vous pouvez examiner ces fichiers générés à l'aide d'outils, tels que [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).  
  
 L'utilisation d'Aximp.exe pour générer un assembly .NET pour le contrôle ActiveX WebBrowser \(shdocvw.dll\) n'est pas prise en charge.  
  
 L'exécution d'Aximp.exe sur shdocvw.dll créera toujours un autre fichier nommé shdocvw.dll dans le répertoire à partir duquel l'outil est exécuté.  Si le fichier généré est placé dans le répertoire Documents and Settings, cela perturbe le fonctionnement de Microsoft Internet Explorer et de l'Explorateur Windows.  Lorsque l'ordinateur est redémarré, Windows recherche une copie de shdocvw.dll dans le répertoire Documents and Settings avant de regarder dans le répertoire system32.  Il utilise la copie trouvée dans Documents and Settings et essaie de charger les wrappers managés.  Internet Explorer et l'Explorateur Windows ne fonctionnent pas correctement, car ils s'appuient sur le moteur de rendu figurant dans la version de shdocvw.dll qui se trouve dans le répertoire system32.  Si ce problème survient, supprimez la copie de shdocvw.dll qui se trouve dans le répertoire Documents and Settings, puis redémarrez votre ordinateur.  
  
 L'utilisation d'Aximp.exe avec shdocvw.dll pour créer un assembly .NET en vue de son utilisation dans le développement d'une application peut également poser problème.  Dans ce cas, votre application chargera la version système de shdocvw.dll ainsi que la version générée, et pourrait donner la priorité à la version système.  Dans ce cas, lorsque vous essayez de charger une page Web dans le contrôle WebBrowser ActiveX, une boîte de dialogue Ouvrir\/Enregistrer peut s'afficher.  Si l'utilisateur clique sur **Ouvrir**, la page Web s'ouvre dans Internet Explorer.  Cela ne se produit que sur les ordinateurs exécutant Internet Explorer version 6 ou antérieure.  Pour éviter ce problème, utilisez le contrôle <xref:System.Windows.Forms.WebBrowser> managé ou utilisez [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pour générer le fichier shdocvw.dll managé, comme décrit dans [How to: Add References to Type Libraries](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md).  
  
## Exemple  
 La commande suivante génère MediaPlayer.dll et AxMediaPlayer.dll pour le contrôle Media Player `msdxm.ocx`.  
  
```  
aximp c:\systemroot\system32\msdxm.ocx  
```  
  
## Voir aussi  
 [Tools](../../../docs/framework/tools/index.md)   
 [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)