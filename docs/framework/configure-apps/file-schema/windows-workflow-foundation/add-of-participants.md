---
title: '&lt;add&gt; de &lt;participants&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0671f7f792c0b9a54190fa1144fcbe8caf6663e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltparticipantsgt"></a>&lt;add&gt; de &lt;participants&gt;
Configurez un participant au suivi qui écoute les enregistrements de suivi émis directement du runtime et les traite en fonction de sa configuration. Cela inclut l'écriture dans une sortie spécifique (par exemple, un fichier, une console ou le suivi d'événements pour Windows [ETW]), le traitement/regroupement des enregistrements ou toute autre combinaison requise.  
  
 Pour plus d’informations de suivi de flux de travail et les participants de suivi, consultez [suivi et traçage de Workflow](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) et [les participants au suivi](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).  
  
\<system.serviceModel >  
\<suivi >  
\<participants >  
\<add>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Élément|Description|  
|-------------|-----------------|  
|name|Chaîne qui spécifie le nom d'un participant au suivi.|  
|profileName|Chaîne qui spécifie le nom du modèle de suivi qui définit les enregistrements de suivi auxquels le participant au suivi s'est abonné.|  
|type|Chaîne qui spécifie le type d'un participant au suivi.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<participants >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|Liste de participants au suivi|  
  
## <a name="remarks"></a>Notes  
 Les participants au suivi permettent d'obtenir les données de suivi émises du flux de travail et de les stocker dans différents médias. De la même manière, tout post-traitement effectué sur les enregistrements de suivi peut également être réalisé dans le participant au suivi.  
  
 Plusieurs participants au suivi peuvent consommer les événements de suivi simultanément. Chaque participant au suivi peut être associé à un modèle de suivi différent.  
  
 Un participant au suivi standard est fourni, il écrit les enregistrements de suivi dans une session ETW. Le participant est configuré sur un service de flux de travail en ajoutant un comportement spécifique au suivi dans un fichier de configuration. L'activation d'un participant au suivi ETW permet d'afficher les enregistrements de suivi dans l'Observateur d'événements. Si cela ne répond pas à vos besoins, vous pouvez également écrire un participant de suivi personnalisé.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant présente la configuration du participant au suivi ETW standard dans le fichier Web.config.  
  
 L’Id de fournisseur par le Participant de suivi ETW pour écrire les enregistrements de suivi ETW est défini dans le  **\<diagnostics >** section. Un profil est associé au participant au suivi pour spécifier les enregistrements de suivi auxquels il est abonné. Cela est défini par le **profileName** attribut de la  **\<Ajouter >** élément. Une fois qu’ils sont définis, le participant au suivi est ajouté à la  **\<etwTracking >** comportement de service. Les participants au suivi sélectionnés sont ajoutés aux extensions de l’instance de flux de travail, afin qu’ils commencent à recevoir les enregistrements de suivi.  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [Suivi et traçage de workflow](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Participants de suivi](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
