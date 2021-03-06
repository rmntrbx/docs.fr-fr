---
title: '&lt;filtre&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 186c511cd8a69cef5e30e369641628a10a0972d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt"></a>&lt;filtre&gt;

Définit un filtre de routage, qui détermine le type de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> à utiliser lors de l'évaluation des messages entrants, ainsi que toutes les données et paramètres de prise en charge requis par le filtre.

\<system.serviceModel > \<routage > \<filtres > \<filtre >

## <a name="syntax"></a>Syntaxe

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a>Attributs et éléments

Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.

### <a name="attributes"></a>Attributs

| Attribut  | Description |
| ---------- | ----------- |
| customType | Chaîne qui contient le nom qualifié complet du type personnalisé à utiliser comme filtre. Si `filterType` a la valeur `custom`, cet attribut contient le nom de type qualifié complet de la classe à créer.  `filterData`peut également contenir des valeurs à utiliser lors de l’évaluation du filtre de type personnalisé. |
| filterData | Chaîne qui contient la données de filtre. Pour plus d'informations sur la spécification de cet attribut, consultez <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Chaîne qui contient le type de filtre. Cet attribut est de type <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Pour plus d'informations sur l'utilisation de cet attribut avec l'attribut `filterData`, consultez <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Chaîne qui contient le nom unique de cet élément de filtre. |

### <a name="child-elements"></a>Éléments enfants

Aucun.

### <a name="parent-elements"></a>Éléments parents

| Élément | Description |
| ------- | ----------- |
| [\<routage >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Une section de configuration pour définir un ensemble de filtres de routage, qui détermine le type de [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> à utiliser lors de l’évaluation des messages entrants. |

## <a name="see-also"></a>Voir aussi

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
