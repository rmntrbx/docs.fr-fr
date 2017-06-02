---
title: "Liaison de donn&#233;es et Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "contrôles dépendants, Windows Forms"
  - "données (Windows Forms), liaison de données complexe"
  - "données (Windows Forms), liaison de données"
  - "données (Windows Forms), liaison de données simple"
  - "liaison de données, Windows Forms"
  - "contrôles liés aux données, Windows Forms"
  - "tables de correspondance, liaison de données"
  - "listes maître/détails"
  - "rapports, Windows Forms"
  - "contrôles Windows Forms, liaison de données"
ms.assetid: 419aac5e-819b-4aad-88b0-73a2f8c0bd27
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Liaison de donn&#233;es et Windows Forms
Dans Windows Forms, vous pouvez créer des liaisons avec des sources de données traditionnelles, mais aussi avec quasiment toute structure contenant des données.  Vous pouvez créer une liaison avec un tableau de valeurs que vous calculez au moment de l'exécution, que vous lisez depuis un fichier ou que vous dérivez de valeurs d'autres contrôles.  
  
 De plus, vous pouvez lier n'importe quelle propriété de n'importe quel contrôle à la source de données.  Dans une liaison de données traditionnelle, vous liez généralement la propriété d'affichage \(par exemple, la propriété <xref:System.Windows.Forms.Control.Text%2A> d'un contrôle <xref:System.Windows.Forms.TextBox>\) à la source de données.  Avec le [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], vous avez également la possibilité de définir d'autres propriétés via la liaison de données.  Vous pouvez utiliser des liaisons pour effectuer les tâches suivantes :  
  
-   Définir le graphisme d'un contrôle d'image  
  
-   Définir la couleur d'arrière\-plan d'un ou plusieurs contrôles  
  
-   Définition de la taille des contrôles  
  
 La liaison de données permet de définir automatiquement toute propriété d'un contrôle de formulaire accessible au moment de l'exécution.  
  
## Types de liaisons de données  
 Windows Forms peut utiliser deux types de liaisons de données : les liaisons simples et les liaisons complexes.  Chaque type a ses propres avantages.  
  
|Type de liaison de données|Description|  
|--------------------------------|-----------------|  
|Liaison de données simple|Capacité d'un contrôle à créer une liaison avec un élément de données, tel qu'une valeur dans une colonne d'une table de dataset.  Il s'agit du type de liaison typique des contrôles tels que <xref:System.Windows.Forms.TextBox> ou <xref:System.Windows.Forms.Label>, qui n'affichent généralement qu'une seule valeur.  En réalité, n'importe quelle propriété d'un contrôle peut être liée à un champ d'une base de données.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] propose une prise en charge étendue pour cette fonctionnalité.<br /><br /> Pour plus d'informations, consultez :<br /><br /> -   [Interfaces participant à la liaison de données](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)<br />-   [Comment : naviguer au sein des données dans les Windows Forms](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)<br />-   [Comment : créer un contrôle à liaison simple dans un Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)|  
|Liaison de données complexe|Capacité d'un contrôle à lier plusieurs éléments de données, généralement plusieurs enregistrements d'une base de données.  La liaison complexe est également appelée liaison basée sur des listes.  Des contrôles qui prennent en charge la liaison complexe sont, par exemple, <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.ListBox> et <xref:System.Windows.Forms.ComboBox>.  Pour obtenir un exemple de liaison de données complexe, consultez [Comment : lier un contrôle ComboBox ou ListBox Windows Forms aux données](../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md).|  
  
## Composant BindingSource  
 Pour simplifier la liaison de données, Windows Forms permet de lier une source de données au composant <xref:System.Windows.Forms.BindingSource>, puis de lier les contrôles à <xref:System.Windows.Forms.BindingSource>.  Vous pouvez utiliser <xref:System.Windows.Forms.BindingSource> dans des scénarios de liaison simple ou complexe.  Dans les deux cas, <xref:System.Windows.Forms.BindingSource> joue le rôle d'intermédiaire entre la source de données et les contrôles liés qui fournissent des services de notification de modifications et de gestion des devises, entre autres services.  
  
## Scénarios courants impliquant des liaisons de données  
 Quasiment toutes les applications commerciales utilisent des informations lues à partir de sources de données d'un type quelconque, généralement au moyen de liaisons de données.  La liste suivante présente quelques exemples de scénarios courants qui utilisent la liaison de données comme méthode de présentation et de manipulation des données.  
  
|Scénario|Description|  
|--------------|-----------------|  
|Création de rapports|Les rapports permettant d'afficher et de synthétiser vos données dans un document imprimé.  Il est très courant de créer un rapport à partir du contenu sélectionné d'une source de données en vue de l'afficher à l'écran ou de l'imprimer.  Les rapports les plus couramment créés sont les listes, les factures et les résumés.  Les éléments sont généralement organisés sous forme de colonnes de listes, avec des sous\-éléments sous chacun d'eux. Toutefois, vous devez choisir la disposition qui convient le mieux à vos données.|  
|Entrée de données|Les formulaires de saisie de données sont couramment utilisés pour entrer de grandes quantités de données associées ou pour demander aux utilisateurs de saisir des informations.  Les utilisateurs peuvent entrer des informations ou choisir parmi des options au moyen de cases à cocher, de cases d'option, de listes déroulantes et de zones de texte.  Les informations sont ensuite envoyées, puis stockées dans une base de données, dont la structure est basée sur les informations entrées.|  
|Relation Maître\/Détail|Une application Maître\/Détail est un format qui permet de consulter des données associées.  Il s'agit de deux tables de données liées par une relation. Un exemple classique est celui de la table "Clients" et de la table "Commandes" qui sont liées par une relation permettant d'associer les clients aux commandes qu'ils ont passées.  Pour plus d'informations sur la création d'une application Maître\/Détail avec deux contrôles <xref:System.Windows.Forms.DataGridView> Windows Forms, consultez [Comment : créer un formulaire maître\/détail utilisant deux contrôles DataGridView Windows Form](../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)|  
|Table de choix|Un autre scénario courant de manipulation et de présentation des données est celui de la table de choix.  Souvent, dans le cadre d'un affichage de données plus important, un contrôle <xref:System.Windows.Forms.ComboBox> est utilisé pour afficher et manipuler des données.  Ce qu'il faut retenir, c'est que les données affichées dans le contrôle <xref:System.Windows.Forms.ComboBox> sont différentes de celles écrites dans la base de données.  Par exemple, si vous avez un contrôle <xref:System.Windows.Forms.ComboBox> qui affiche les articles disponibles dans une épicerie, vous préférerez sans doute voir le nom des produits \(pain, lait, œufs\).  Toutefois, afin de faciliter l'extraction d'informations et dans un objectif de normalisation des bases de données, vous stockeriez probablement les informations relatives aux éléments d'une commande donnée sous forme de numéros d'article \(\#501, \#603, etc.\).  Par conséquent, il existe un lien implicite entre le "nom convivial" de l'article dans le contrôle <xref:System.Windows.Forms.ComboBox> de votre formulaire, et le numéro d'article associé qui est présent dans la commande.  C'est tout l'intérêt d'une recherche dans une table.  Pour plus d'informations, consultez [Comment : créer une table de correspondance avec le composant BindingSource Windows Forms](../../../docs/framework/winforms/controls/how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component.md).|  
  
## Voir aussi  
 <xref:System.Windows.Forms.Binding>   
 [Liaison de données Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Comment : lier le contrôle DataGrid Windows Forms à une source de données](../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Composant BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)