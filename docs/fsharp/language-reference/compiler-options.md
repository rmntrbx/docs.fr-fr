---
title: Options du compilateur (F#)
description: 'Utilisez les options du compilateur de ligne de commande F # pour contrôler la compilation de vos applications F # et bibliothèques.'
keywords: visual f#, f#, programmation fonctionnelle
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c797cf0b-5953-4053-8626-0558e9eaf10f
ms.openlocfilehash: 23731832141bc2f74a04c5f4027fc210b5589537
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2018
---
# <a name="compiler-options"></a>Options du compilateur

Cette rubrique décrit les options de ligne de commande du compilateur pour le compilateur F #, fsc.exe. L’environnement de compilation peut également être contrôlé en définissant les propriétés du projet.


## <a name="compiler-options-listed-alphabetically"></a>Options du compilateur classées par ordre alphabétique
Le tableau suivant montre les options du compilateur classées par ordre alphabétique. Certaines des options du compilateur F # sont similaires aux options du compilateur c#. Si tel est le cas, un lien vers la rubrique d’options du compilateur c# est fourni.



|Option du compilateur|Description|
|---------------|-----------|
|**-a****&lt;output-filename&gt;**|Génère une bibliothèque et spécifie son nom de fichier. Cette option est une forme abrégée de **--target : library ***&lt;nom de fichier&gt;**.|
|**--baseaddress :&lt;chaîne&gt;**|Spécifie l’adresse de base de la bibliothèque à générer.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;baseaddress &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/2fdbz5xd.aspx).|
|**page de codes-- :&lt;int&gt;**|Spécifie la page de codes utilisée pour lire les fichiers de code source.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;page de codes &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/w0kyekyh.aspx).|
|**--consolecolors**|Spécifie que les erreurs et avertissements utilisent texte coloré sur la console.|
|**--crossoptimize**[**+**&#124;**-**]|Active ou désactive les optimisations intermodules.|
|**--delaysign**[**+**&#124;**-**]|Signe l’assembly en utilisant uniquement la partie publique de la clé de nom fort.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;delaysign &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/ta1sxwy8.aspx).|
|**--checked**[**+**&#124;**-**]|Active ou désactive la génération de contrôles de dépassement.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;vérifiée &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/h25wtyxf.aspx).|
|**--debug**[**+**&#124;**-**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**--debug**:[**full**&#124;**pdbonly**]<br /><br />**-g:** [**full**&#124;**pdbonly**]|Active ou désactive la génération des informations de débogage ou spécifie le type d’informations de débogage à générer. La valeur par défaut est plein, ce qui permet l’attachement à un programme en cours d’exécution. Choisissez **pdbonly** pour obtenir des informations de débogage limitées stockées dans un fichier pdb (base de données du programme).<br /><br />Équivalent à l’option du compilateur c# du même nom. Pour plus d'informations, consultez<br /><br />[&#47;déboguer &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/8cw0bt21.aspx).|
|**--définir :&lt;chaîne&gt;**<br /><br />**-d:&lt;chaîne&gt;**|Définit un symbole pour une utilisation dans une compilation conditionnelle.|
|**--deterministic**[**+**&#124;**-**]|Générer un assembly déterministe (y compris le GUID de version de module et timestamp).  Cela ne peut pas être utilisé avec les numéros de version générique et prend uniquement en charge les types de débogage incorporés et portables|
|**--doc:&lt;xmldoc-filename&gt;**|Indique au compilateur de générer des commentaires de documentation XML dans le fichier spécifié. Pour plus d’informations, consultez [Documentation XML](xml-documentation.md).<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;doc &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/3260k4x7.aspx).|
|**--fullpaths**|Indique au compilateur de générer des chemins d’accès complets.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;/fullpaths &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/d315xc66.aspx).|
|**--help**<br /><br />**-?**|Affiche les informations d’utilisation, y compris une brève description de toutes les options du compilateur.|
|**--highentropyva**[**+**&#124;**-**]|Activer ou désactiver la randomisation du format d’espace d’adresse d’entropie élevée (ASLR), une fonctionnalité de sécurité renforcée. Le système d’exploitation rend aléatoire les emplacements dans la mémoire dans lequel l’infrastructure pour les applications (par exemple, la pile et d’un segment de mémoire) est chargé. Si vous activez cette option, les systèmes d’exploitation peut utiliser cette fonctionnalité de randomisation à utiliser l’adresse 64 bits complète-espace sur un ordinateur 64 bits.|
|**--keycontainer :&lt;chaîne&gt;**|Spécifie un conteneur de clé de nom fort.|
|**--keyfile:&lt;filename&gt;**|Spécifie le nom d’un fichier de clé publique pour signer l’assembly généré.|
|**--lib:&lt;folder-name&gt;**<br /><br />**-I:&lt;folder-name&gt;**|Spécifie un répertoire dans lequel rechercher les assemblys référencés.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;lib &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/s5bac5fx.aspx).|
|**--linkresource**:**&lt;resource-info&gt;**|Lie une ressource spécifiée à l’assembly. Le format des informations de ressource est *nom de fichier*[,*nom*[,*public*&#124;*privé*]]<br /><br />Liaison d’une ressource unique avec cette option est une alternative à l’incorporation d’un fichier de ressources entier avec la **--ressource** option.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;/linkresource &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/xawyf94k.aspx).|
|**--mlcompatibility**|Ignore les avertissements qui apparaissent lorsque vous utilisez des fonctionnalités conçues pour assurer la compatibilité avec d’autres versions de ML.|
|**--noframework**|Désactive la référence par défaut à l’assembly .NET Framework.|
|**--nointerfacedata**|Indique au compilateur d’omettre la ressource qu’il ajoute normalement à un assembly qui inclut F #-métadonnées spécifiques.|
|**--nologo**|N’affiche pas le texte de bannière lors du lancement du compilateur.|
|**--nooptimizationdata**|Indique au compilateur pour inclure uniquement les optimisation essentielle pour l’implémentation de constructions inline. Interdit une incorporation entre modules mais améliore la compatibilité binaire.|
|**--nowin32manifest**|Indique au compilateur d’omettre le manifeste Win32 par défaut.|
|**--nowarn :&lt;int-liste&gt;**|Désactive les avertissements spécifiques répertoriés par nombre. Séparez chaque numéro d’avertissement par une virgule. Vous pouvez découvrir le numéro d’avertissement pour chaque avertissement à partir de la sortie de la compilation.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;/nowarn &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/7f28x9z3.aspx).|
|**--optimize**[**+**&#124;**-**]**[&lt;string-list&gt;]**<br /><br />**-O[+&#124;-] [&lt;string-list&gt;]**|Active ou désactive les optimisations. Certaines options d’optimisation peuvent être désactivées ou activées de manière sélective en les répertoriant. Il s’agit : **nojitoptimize**, **nojittracking**, **nolocaloptimize**, **nocrossoptimize**, **notailcalls**.|
|**--out :&lt;nom du fichier de sortie&gt;**<br /><br />**-o:&lt;nom du fichier de sortie&gt;**|Spécifie le nom de l’assembly compilé ou le module.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;hors &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/bw3t50f3.aspx).|
|**--pdb :&lt;nom de fichier pdb&gt;**|Nommer le fichier PDB (base de données du programme) de débogage sortie. Cette option s’applique uniquement lorsque **--debug** est également activée.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;pdb &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/ms228625.aspx).|
|**--platform:&lt;platform-name&gt;**|Spécifie que le code généré sera uniquement exécutée sur la plateforme spécifiée (**x86**, **Itanium**, ou **x64**), ou, si le nom de la plateforme **anycpu**est sélectionnée, spécifie que le code généré peut s’exécuter sur n’importe quelle plateforme.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;plateforme &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/zekwfyz4.aspx).|
|**--preferreduilang :&lt;lang&gt;**| Spécifie le nom de culture de langue préférée de sortie (par exemple, es-ES, ja-JP). |
|**--quotations-debug**|Spécifie que les informations de débogage supplémentaires doivent être émises pour les expressions qui sont dérivées de littéraux de guillemets F # et répercutées définitions. Les informations de débogage sont ajoutées pour les attributs personnalisés d’un nœud d’arborescence de l’expression F #. Consultez [Quotations de Code](code-quotations.md) et [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--référence :&lt;filename de l’assembly&gt;**<br /><br />**-r** &lt;**assembly-filename&gt;**|Rend le code à partir d’un assembly F # ou .NET Framework disponibles au code qui est compilé.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;référence &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/yabyz3h4.aspx).|
|**--resource:&lt;resource-filename&gt;**|Incorpore un fichier de ressources managé dans l’assembly généré.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;ressource &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/c0tyye07.aspx).|
|**--sig**:&lt;**signature-filename&gt;**|Génère un fichier de signature basé sur l’assembly généré. Pour plus d’informations sur les fichiers de signature, consultez [Signatures](signatures.md).|
|**--simpleresolution**|Spécifie que les références d’assembly doivent être résolus à l’aide de règles Mono basées sur le répertoire plutôt que la résolution MSBuild. La valeur par défaut est d’utiliser la résolution MSBuild, sauf lors de l’exécution sous Mono.|
|**--standalone**|Spécifie pour produire un assembly qui contient l’ensemble de ses dépendances afin qu’elle s’exécute par lui-même sans recourir à des assemblys supplémentaires, telles que la bibliothèque F #.|
|**--staticlink :&lt;-nom de l’assembly**&gt;|Lie statiquement l’assembly donné et toutes les DLL référencées qui dépendent de cet assembly. Utilisez le nom de l’assembly, pas le nom de la DLL.|
|**--subsystemversion**|Spécifie la version du sous-système du système d’exploitation à utiliser par l’exécutable généré. Utilisez 6.02 pour Windows 8.1, 6.01 pour Windows 7, 6,00 pour Windows Vista. Cette option seulement s’applique aux exécutables, pas les DLL et doive être utilisée uniquement si votre application dépend des fonctionnalités de sécurité spécifiques disponibles uniquement sur certaines versions de système d’exploitation. Si cette option est utilisée, et un utilisateur tente d’exécuter votre application sur une version antérieure du système d’exploitation, il échouera avec un message d’erreur.|
|**--tailcalls**[**+**&#124;**-**]|Active ou désactive l’utilisation de l’instruction de langage intermédiaire de fin, ce qui entraîne le frame de pile être réutilisées pour les fonctions récursives tail. Cette option est activée par défaut.|
|**--target**:[**exe** &#124; **winexe** &#124; **library** &#124; **module** ] **&lt;output-filename&gt;**|Spécifie le type et le nom du code compilé généré.<ul><li>**exe** signifie une application console.<br /></li><li>**winexe** signifie une application Windows, qui diffère de l’application de console dans la mesure où il n’a pas d’entrée/sortie flux standard (stdin, stdout et stderr) définis.<br /></li><li>**bibliothèque** est un assembly sans un point d’entrée.<br /></li><li>**module** est un module .NET Framework (.netmodule), qui peut être combiné ultérieurement avec d’autres modules dans un assembly.<br /></li><ul/>Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;cible &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/6h25dztx.aspx).|
|**--times**|Affiche les informations de temporisation pour la compilation.|
|**--utf8output**|Permet d’imprimer la sortie du compilateur dans l’encodage UTF-8.|
|**--avertir :&lt;niveau d’avertissement&gt;**|Définit un niveau d’avertissement (de 0 à 5). Le niveau par défaut est 3. Chaque avertissement est émis à un niveau en fonction de sa gravité. Niveau 5 donne les avertissements graves, de plus, mais inférieur au niveau 1.<br /><br />Avertissements de niveau 5 sont : 21 (utilisation récursive vérifiée lors de l’exécution), 22 (**permettent de rec** évaluée dans le désordre), 45 (abstraction complète) et 52 (la copie). Tous les autres avertissements sont de niveau 2.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;avertir &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/13b90fz7.aspx).|
|**--warnon:&lt;int-list&gt;**|Activer des avertissements spécifiques qui peuvent être désactivés par défaut ou désactivé par une autre option de ligne de commande. Dans F # 3.0, seulement l’avertissement 1182 (variables inutilisées) est désactivée par défaut.|
|**--warnaserror**[**+**&#124;**-**] [**&lt;int-list&gt;**]|Active ou désactive l’option de signalement des avertissements comme des erreurs. Vous pouvez fournir des numéros d’avertissement spécifiques pour être désactivé ou activé. Options plus loin dans la ligne de commande remplacent les options précédemment dans la ligne de commande. Par exemple, pour spécifier les avertissements que vous ne souhaitez pas signalés comme erreurs, spécifiez **--warnaserror +--warnaserror- :&lt;int-list&gt;**.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;/warnaserror &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/406xhdz3.aspx).|
|**--win32manifest:manifest-filename**|Ajoute un fichier manifeste Win32 à la compilation. Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;win32manifest &#40;C&#35; Options du compilateur&#41;](https://msdn.microsoft.com/library/bb545961.aspx).|
|**--win32res:resource-filename**|Ajoute un fichier de ressources Win32 à la compilation.<br /><br />Cette option du compilateur est équivalente à l’option du compilateur c# du même nom. Pour plus d’informations, consultez [ &#47;win32res (&#40;C & #35) ; Options du compilateur&#41;](https://msdn.microsoft.com/library/8f2f5x2e.aspx).|

## <a name="related-topics"></a>Rubriques connexes


|Titre|Description|
|-----|-----------|
|[Options F# Interactive](fsharp-interactive-options.md)|Décrit les options de ligne de commande pris en charge par l’interpréteur F #, fsi.exe.|
|[Informations de référence sur les propriétés de projet](/visualstudio/ide/reference/project-properties-reference)|Décrit l’interface utilisateur pour les projets, y compris les pages de propriétés de projet qui fournissent des options de génération.|
