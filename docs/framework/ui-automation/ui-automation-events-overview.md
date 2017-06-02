---
title: "UI Automation Events Overview | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, providers"
  - "UI Automation, events"
  - "clients, UI Automation"
  - "events, UI Automation"
  - "providers, UI Automation"
  - "UI Automation, clients"
ms.assetid: 69eebd8b-39ed-40e7-93cc-4457c4caf746
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# UI Automation Events Overview
> [!NOTE]
>  Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>. Pour obtenir les dernières informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [API Windows Automation : UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 La notification d'événements [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] est une fonctionnalité clé pour les technologies d'assistance comme les lecteurs d'écran et les loupes. Ces clients UI Automation suivent les événements déclenchés par les fournisseurs UI Automation quand quelque chose se produit dans [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] et utilisent les informations pour avertir les utilisateurs finaux.  
  
 L'efficacité est améliorée en permettant aux applications fournisseurs de déclencher des événements de manière sélective, selon que des clients sont abonnés à ces événements ou non, si aucun client n'écoute d'événement.  
  
<a name="Types_of_Events"></a>   
## Types d'événements  
 Les événements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sont répartis dans les catégories suivantes.  
  
|Événement|Description|  
|---------------|-----------------|  
|Modification de propriété|Déclenché quand une propriété sur un modèle de contrôle ou sur un élément [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] change. Par exemple, si un client doit surveiller le contrôle de case à cocher d'une application, il peut s'inscrire pour écouter un événement de modification de propriété sur la propriété <xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A>. Quand le contrôle de case à cocher est coché ou décoché, le fournisseur déclenche l'événement et le client peut agir de manière appropriée.|  
|Action d'élément|Déclenché quand une modification de l'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] résulte de l'utilisateur final ou d'une activité de programmation ; par exemple, quand un utilisateur clique sur un bouton ou l'appelle via <xref:System.Windows.Automation.InvokePattern>.|  
|Modification de la structure|Déclenché quand la structure de l'arborescence [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] change. La structure change quand de nouveaux éléments d'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] sont visibles, masqués ou supprimés du bureau.|  
|Modification globale du bureau|Déclenché quand des actions d'intérêt global pour le client se produisent, par exemple quand le focus passe d'un élément à un autre ou qu'une fenêtre se ferme.|  
  
 Certains événements ne signifient pas nécessairement que l'état de l'interface utilisateur a changé. Par exemple, si l'utilisateur passe à un champ de saisie de texte via une tabulation, puis clique sur un bouton pour mettre à jour le champ, un `TextChangedEvent` est déclenché même si l'utilisateur n'a pas réellement changé le texte. Pendant le traitement d'un événement, une application cliente peut être amenée à vérifier ce qui a réellement changé avant d'agir.  
  
 Les événements suivants peuvent être déclenchés même quand l'état de l'interface utilisateur n'a pas changé.  
  
-   `AutomationPropertyChangedEvent` \(selon la propriété qui a changé\)  
  
-   `ElementSelectedEvent`  
  
-   `InvalidatedEvent`  
  
-   `TextChangedEvent`  
  
<a name="UI_Automation_Event_Identifiers"></a>   
## Identificateurs d'événements UI Automation  
 Les événements [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sont identifiés par des objets <xref:System.Windows.Automation.AutomationEvent>. La propriété <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> contient une valeur qui identifie de manière unique le type d'événement.  
  
 Les valeurs possibles pour <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> figurent dans le tableau ci\-dessous, ainsi que le type utilisé pour les arguments d'événement. Notez que les identificateurs utilisés par les clients et les fournisseurs sont des champs de même nom issus de classes différentes.  
  
|Identifiant du client|Identifiant du fournisseur|Type d'arguments d'événement|  
|---------------------------|--------------------------------|----------------------------------|  
|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|  
|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionPattern.InvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.InvokePattern.InvokedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.LayoutInvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPattern.TextChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPattern.TextSelectionChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationPropertyChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.StructureChangedEventArgs>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.WindowClosedEventArgs>|  
  
<a name="UI_Automation_Event_Arguments"></a>   
## Arguments d'événement UI Automation  
 Les classes suivantes encapsulent des arguments d'événement.  
  
|Classe|Description|  
|------------|-----------------|  
|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|Contient des informations concernant le chargement asynchrone de contenu, notamment le pourcentage de chargement effectué.|  
|<xref:System.Windows.Automation.AutomationEventArgs>|Contient des informations sur un événement simple qui ne nécessite pas de données supplémentaires.|  
|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|Contient des informations sur une modification du focus d'entrée d'un élément à un autre. Les événements de ce type sont déclenchés par le système [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], pas par les fournisseurs.|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|Contient des informations sur la modification de la valeur d'une propriété d'un élément ou d'un modèle de contrôle.|  
|<xref:System.Windows.Automation.StructureChangedEventArgs>|Contient des informations sur une modification dans l'arborescence [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|<xref:System.Windows.Automation.WindowClosedEventArgs>|Contient des informations sur une fermeture de fenêtre.|  
  
 Toutes les classes d'argument d'événement contiennent un membre <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>. Cet identificateur est encapsulé dans un <xref:System.Windows.Automation.AutomationEvent>.  
  
 Les objets <xref:System.Windows.Automation.AutomationEvent> utilisés pour identifier des événements sont obtenus par les fournisseurs de champs dans <xref:System.Windows.Automation.AutomationElementIdentifiers> et des classes d'identificateur de modèle de contrôle telles que <xref:System.Windows.Automation.DockPatternIdentifiers>. Les champs équivalents sont obtenus par les applications clientes à partir des champs d'<xref:System.Windows.Automation.AutomationElement> et des classes de modèle de contrôle telles que <xref:System.Windows.Automation.DockPattern>.  
  
 Pour obtenir la liste des identificateurs d’événement, consultez [UI Automation Events for Clients](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md).  
  
## Voir aussi  
 [UI Automation Events for Clients](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md)   
 [Server\-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)   
 [Subscribe to UI Automation Events](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)