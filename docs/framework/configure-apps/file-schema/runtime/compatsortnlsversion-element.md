---
title: "&#201;l&#233;ment &lt;CompatSortNLSVersion&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "<CompatSortNLSVersion> (élément)"
  - "CompatSortNLSVersion (élément)"
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# &#201;l&#233;ment &lt;CompatSortNLSVersion&gt;
Spécifie que le runtime doit utiliser des ordres de tri hérités lors de l'exécution de comparaisons de chaînes.  
  
## Syntaxe  
  
```  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### Attributs  
  
|Attribut|Description|  
|--------------|-----------------|  
|`enabled`|Attribut requis.<br /><br /> Spécifie l'ID de paramètres régionaux dont l'ordre de tri doit être utilisé.|  
  
## Attribut enabled  
  
|Valeur|Description|  
|------------|-----------------|  
|4096|ID de paramètres régionaux qui représente un ordre de tri secondaire.  Dans ce cas, 4096 représente l'ordre de tri de [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] et versions antérieures.|  
  
### Éléments enfants  
 Aucun.  
  
### Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|`configuration`|Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.|  
|`runtime`|Contient des informations sur les options d'initialisation du runtime.|  
  
## Notes  
 Dans la mesure où la comparaison de chaînes, le tri et les opérations de choix de la casse effectuées par la classe <xref:System.Globalization.CompareInfo?displayProperty=fullName> dans [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] sont conformes à la norme Unicode 5.1, les résultats des méthodes de comparaison de chaînes telles que <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=fullName> et <xref:System.String.LastIndexOf%28System.String%29?displayProperty=fullName> peuvent différer des versions précédentes du .NET Framework.  Si votre application dépend d'un comportement hérité, vous pouvez restaurer la comparaison de chaînes et les règles de tri utilisées dans [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] et versions antérieures en incluant l'élément `<CompatSortNLSVersion>` dans le fichier de configuration de l'application.  
  
> [!IMPORTANT]
>  La restauration de la comparaison de chaînes héritées et des règles de tri requiert également que la bibliothèque de liens dynamiques sort00001000.dll soit disponible sur le système local.  
  
 Vous pouvez également utiliser des règles de tri et de comparaison de chaîne héritées dans un domaine d'application spécifique en passant la chaîne « NetFx40\_Legacy20SortingBehavior » à la méthode <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> lorsque vous créez le domaine d'application.  
  
## Exemple  
 L'exemple suivant instancie deux objets <xref:System.String> et appelle la méthode <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=fullName> pour les comparer en utilisant les conventions de la culture actuelle.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 Lorsque vous exécutez l'exemple sur [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la sortie suivante s'affiche.  
  
```  
sta follows a in the sort order.  
```  
  
 Cela est complètement différent de la sortie qui s'affiche lorsque vous exécutez l'exemple sur [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
sta equals a in the sort order.  
```  
  
 Toutefois, si vous ajoutez le fichier de configuration suivant au répertoire de l'exemple, puis exécutez l'exemple sur [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la sortie est identique à celle produite par l'exemple lorsqu'il est exécuté sur [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## Voir aussi  
 [Schéma des paramètres d'exécution](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Schéma des fichiers de configuration](../../../../../docs/framework/configure-apps/file-schema/index.md)