---
title: ".NET Framework Tools | Microsoft Docs"
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
  - "command line, .NET Framework tools"
  - ".NET Framework, tools"
  - "tools [.NET Framework]"
  - "running .NET Framework tools"
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
caps.latest.revision: 65
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 63
---
# .NET Framework Tools
Les outils du .NET Framework facilitent la création, le déploiement et la gestion d'applications et de composants qui ciblent le .NET Framework.  
  
 La plupart des outils .NET Framework décrits dans cette section sont installés automatiquement avec Visual Studio. \(Pour plus d’informations sur l’installation, consultez les [Téléchargements Visual Studio](http://go.microsoft.com/fwlink/?LinkID=325532).\)  
  
 Vous pouvez exécuter tous les outils à partir de la ligne de commande, à l'exception de la visionneuse du cache d'assembly \(Shfusion.dll\). Vous devez accéder à Shfusion.dll à partir de l'Explorateur de fichiers.  
  
 Le meilleur moyen d'exécuter l'outil en ligne de commande consiste à utiliser l'invite de commandes développeur Visual Studio. Ces utilitaires vous permettent d'exécuter facilement les outils, sans naviguer jusqu'au dossier d'installation. Pour plus d'informations, consultez [Invites de commandes](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
> [!NOTE]
>  Certains outils sont spécifiques aux ordinateurs 32 bits ou aux ordinateurs 64 bits. Veillez à exécuter la version appropriée de l'outil pour votre ordinateur.  
  
## Dans cette section  
 [Al.exe \(Assembly Linker\)](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 Génère un fichier qui possède un manifeste de l'assembly issu de modules ou de fichiers de ressources.  
  
 [Aximp.exe \(Windows Forms ActiveX Control Importer\)](../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)  
 Convertit les définitions de types d'une bibliothèque de types COM d'un contrôle ActiveX en contrôle Windows Forms.  
  
 [Caspol.exe \(Code Access Security Policy Tool\)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)  
 Permet d'afficher et de configurer la stratégie de sécurité au niveau de l'ordinateur, de l'utilisateur et de l'entreprise. Dans le [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] et versions ultérieures, cet outil n'affecte pas la stratégie de sécurité d'accès du code \(CAS\), à moins que l'[\<legacyCasPolicy\>élément](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) ait la valeur `true`. Pour plus d'informations, consultez [Modifications de sécurité](../../../docs/framework/security/security-changes.md).  
  
 [Cert2spc.exe \(Software Publisher Certificate Test Tool\)](../../../docs/framework/tools/cert2spc-exe-software-publisher-certificate-test-tool.md)  
 Crée un certificat SPC \(Software Publisher's Certificate\) à partir d'un ou plusieurs certificats X.509. Cet outil ne doit être utilisé qu'à des fins de test.  
  
 [Certmgr.exe \(Certificate Manager Tool\)](../../../docs/framework/tools/certmgr-exe-certificate-manager-tool.md)  
 Gère les certificats, les listes de certificats de confiance \(CTL\) et les listes de révocation de certificats \(CRL\).  
  
 [Clrver.exe \(CLR Version Tool\)](../../../docs/framework/tools/clrver-exe-clr-version-tool.md)  
 Rapporte toutes les versions installées du CLR \(Common Runtime Language\) sur l'ordinateur.  
  
 [CorFlags.exe \(CorFlags Conversion Tool\)](../../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md)  
 Vous permet de configurer la section CorFlags de l'en\-tête d'une image exécutable portable \(PE\).  
  
 [Fuslogvw.exe \(Assembly Binding Log Viewer\)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)  
 Affiche des informations sur les liaisons d'assembly pour vous aider à diagnostiquer ce qui empêche le .NET Framework de trouver l'assembly au moment de l'exécution.  
  
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 Vous permet de visualiser et de manipuler le contenu du Global Assembly Cache et du cache de téléchargement.  
  
 [Ilasm.exe \(IL Assembler\)](../../../docs/framework/tools/ilasm-exe-il-assembler.md)  
 Génère un fichier PE \(exécutable portable\) en langage IL \(Intermediate Language\). Vous pouvez exécuter le fichier exécutable obtenu pour déterminer si le langage IL fonctionne comme prévu.  
  
 [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)  
 Utilise un fichier PE qui contient le code IL \(Intermediate Language\) et crée un fichier texte qu'il peut utiliser en entrée dans l'Assembleur IL \(Ilasm.exe\).  
  
 [Installutil.exe \(Installer Tool\)](../../../docs/framework/tools/installutil-exe-installer-tool.md)  
 Permet d'installer et de désinstaller des ressources serveur en exécutant les composants d'installation d'un assembly spécifié. \(Utilise les classes dans l'espace de noms <xref:System.Configuration.Install>.\) Permet d'installer et de désinstaller des ressources serveur en exécutant les composants d'installation d'un assembly spécifié. \(Utilise les classes dans l'espace de noms <xref:System.Configuration.Install>.\)  
  
 [Lc.exe \(License Compiler\)](../../../docs/framework/tools/lc-exe-license-compiler.md)  
 Lit les fichiers texte qui contiennent des informations de licence et produit un fichier .licenses qui peut être incorporé en tant que ressource dans un exécutable du Common Language Runtime. Lit les fichiers texte qui contiennent des informations de licence et produit un fichier .licenses qui peut être incorporé en tant que ressource dans un exécutable du Common Language Runtime.  
  
 [Mage.exe \(outil Manifest Generation and Editing\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 Permet de créer, de modifier et de signer des manifestes d'application et de déploiement. En tant qu'outil en ligne de commande, Mage.exe peut être exécuté à partir de scripts de commandes et d'autres applications Windows, notamment les applications ASP.NET.  
  
 [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
 Prend en charge les mêmes fonctionnalités que l'outil en ligne de commande Mage.exe, mais utilise une interface utilisateur de type Windows. Prend en charge les mêmes fonctionnalités que l'outil en ligne de commande Mage.exe, mais utilise une interface utilisateur de type Windows.  
  
 [MDbg.exe \(.NET Framework Command\-Line Debugger\)](../../../docs/framework/tools/mdbg-exe.md)  
 Permet aux fournisseurs d'outils et aux développeurs d'applications de trouver et de corriger les bogues dans les programmes qui ont pour cible le Common Language Runtime du .NET Framework. Cet outil utilise l'API de débogage du runtime pour fournir des services de débogage.  
  
 [Mgmtclassgen.exe \(Management Strongly Typed Class Generator\)](../../../docs/framework/tools/mgmtclassgen-exe.md)  
 Permet de générer une classe managée à liaison anticipée pour une classe Windows Management Instrumentation spécifiée \(WMI\).  
  
 [Mpgo.exe \(Managed Profile Guided Optimization Tool\)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)  
 Vous permet d'ajuster les assemblys d'image native en utilisant des scénarios courants d'utilisateurs finaux. Mpgo.exe permet la génération et la consommation des données de profil pour les assemblys d'application d'image native \(pas les assemblys .NET Framework\) à l'aide de scénarios d'apprentissage sélectionnés par le développeur d'applications.  
  
 [Ngen.exe \(Native Image Generator\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)  
 Améliore les performances des applications managées via l'utilisation d'images natives \(fichiers qui contiennent le code machine spécifique au processeur compilé\). Le runtime peut utiliser des images natives du cache plutôt que le compilateur juste\-à\-temps \(JIT\) pour compiler l'assembly d'origine.  
  
 [Peverify.exe \(PEVerify Tool\)](../../../docs/framework/tools/peverify-exe-peverify-tool.md)  
 Permet de vérifier si votre code MSIL \(Microsoft Intermediate Language\) et les métadonnées associées satisfont aux spécifications de cohérence des types. Permet de vérifier si votre code MSIL \(Microsoft Intermediate Language\) et les métadonnées associées satisfont aux spécifications de cohérence des types.  
  
 [Regasm.exe \(Assembly Registration Tool\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 Lit les métadonnées dans un assembly et ajoute les entrées nécessaires au Registre. Cela permet aux clients COM d'apparaître en tant que classes .NET Framework.  
  
 [Regsvcs.exe \(.NET Services Installation Tool\)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)  
 Charge et enregistre un assembly, génère et installe une bibliothèque de types dans une application COM\+ version 1.0 spécifiée et configure les services que vous avez ajoutés par programmation à une classe.  
  
 [Resgen.exe \(Resource File Generator\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 Convertit les fichiers texte \(.txt ou .restext\) et les fichiers .resx \(format de ressources XML\) en fichiers .resources binaires du Common Language Runtime qui peuvent être incorporés dans un exécutable binaire runtime ou compilés en assemblys satellites.  
  
 [SecAnnotate.exe \(.NET Security Annotator Tool\)](../../../docs/framework/tools/secannotate-exe-net-security-annotator-tool.md)  
 Identifie les parties SecurityCritical et SecuritySafeCritical d'un assembly. Identifie les parties `SecurityCritical` et `SecuritySafeCritical` d'un assembly.  
  
 [SignTool.exe \(Sign Tool\)](../../../docs/framework/tools/signtool-exe.md)  
 Signe numériquement les fichiers, vérifie les signatures dans les fichiers et insère un horodatage dans les fichiers.  
  
 [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 Facilite la création d'assemblys avec des noms forts. Cet outil fournit des options de gestion des clés, de génération des signatures et de vérification des signatures.  
  
 [SOS.dll \(SOS Debugging Extension\)](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md)  
 Vous aide à déboguer des programmes managés dans le débogueur WinDbg.exe et dans Visual Studio en fournissant des informations sur l'environnement interne du CLR \(Common Language Runtime\).  
  
 [SqlMetal.exe \(outil de génération de code\)](../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 Génère le code et le mappage pour le composant LINQ to SQL du .NET Framework.  
  
 [Storeadm.exe \(Isolated Storage Tool\)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)  
 Gère le stockage isolé en proposant des options pour répertorier les magasins de l'utilisateur et les supprimer.  
  
 [Tlbexp.exe \(Type Library Exporter\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)  
 Génère une bibliothèque de types décrivant les types définis dans un assembly du Common Language Runtime.  
  
 [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 Convertit les définitions de types présentes dans une bibliothèque de types COM en définitions équivalentes dans un assembly de Common Language Runtime.  
  
 [Winmdexp.exe \(Windows Runtime Metadata Export Tool\)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)  
 Exporte un assembly .NET Framework. compilé comme fichier .winmdobj dans un composant Windows Runtime, qui est empaqueté comme fichier .winmd qui contient à la fois les métadonnées Windows Runtime et des informations d'implémentation.  
  
 [Winres.exe \(Windows Forms Resource Editor\)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 Aide à localiser des ressources d'interface utilisateur \(fichiers .resx ou .resources\) utilisées par les Windows Forms. Vous pouvez traduire des chaînes puis dimensionner, déplacer et masquer les contrôles comme vous le souhaitez afin de placer les chaînes localisées.  
  
## Rubriques connexes  
 [Tools](../Topic/WPF%20Tools.md)  
 Inclut des outils tels que l'outil isXPS Conformance Tool \(isXPS.exe\), les outils de profilage des performances et XamlPad, qui est un éditeur graphique de base pour le langage XAML \(Extensible Application Markup Language\).  
  
 [Outils de Windows Communication Foundation](../../../docs/framework/wcf/tools.md)  
 Inclut des outils qui facilitent la création, le déploiement et la gestion d'applications Windows Communication Foundation \(WCF\).