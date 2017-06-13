---
title: "Mod&#232;le objet de programmation Web HTTP WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed96b5fc-ca2c-4b0d-bdba-d06b77c3cb2a
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Mod&#232;le objet de programmation Web HTTP WCF
Le modèle de programmation Web HTTP WCF permet aux développeurs d'exposer des services Web [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] par le biais de requêtes HTTP de base sans avoir recours à SOAP.  Le modèle de programmation Web HTTP WCF tire parti du modèle d'extensibilité [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] existant.  Il définit les classes suivantes :  
  
 **Modèle de programmation :**  
  
-   <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>  
  
-   <xref:System.ServiceModel.Web.WebGetAttribute>  
  
-   <xref:System.ServiceModel.Web.WebInvokeAttribute>  
  
-   <xref:System.ServiceModel.Web.WebServiceHost>  
  
 **Infrastructure de canaux et de répartiteur :**  
  
-   <xref:System.ServiceModel.WebHttpBinding>  
  
-   <xref:System.ServiceModel.Description.WebHttpBehavior>  
  
 **Points d'extensibilité et classes d'utilitaire :**  
  
-   <xref:System.UriTemplate>  
  
-   <xref:System.UriTemplateTable>  
  
-   <xref:System.ServiceModel.Dispatcher.QueryStringConverter>  
  
-   <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>  
  
## AspNetCacheProfileAttribute  
 En cas d'application à une opération de service, <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> indique le profil de cache de sortie ASP.NET dans le fichier de configuration qui doit être utilisé pour mettre des réponses de l'opération dans le cache de sortie ASP .NET.  Cette propriété accepte un seul paramètre, le nom de profil de cache qui spécifie les paramètres de cache dans le fichier de configuration.  
  
## WebGetAttribute  
 L'attribut <xref:System.ServiceModel.Web.WebGetAttribute> est utilisé pour marquer une opération de service en tant qu'opération répondant aux requêtes HTTP GET.  Il s'agit d'un comportement d'opération passif \(les méthodes <xref:System.ServiceModel.Description.IOperationBehavior> n'ont aucune action\) qui ajoute des métadonnées à la description de l'opération.  L'attribut <xref:System.ServiceModel.Web.WebGetAttribute> n'a aucun effet à moins qu'un comportement recherchant ces métadonnées dans la description de l'opération \(en particulier <xref:System.ServiceModel.Description.WebHttpBehavior>\) soit ajouté à la collection de comportements du service.  L'attribut <xref:System.ServiceModel.Web.WebGetAttribute> accepte les paramètres optionnels indiqués dans le tableau suivant :  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`BodyStyle`|Contrôle si les demandes envoyées à l'opération de service à laquelle l'attribut est appliqué et les réponses reçues en retour doivent être encapsulées.|  
|`RequestFormat`|Contrôle la mise en forme des messages de demande.|  
|`ResponseFormat`|Contrôle la mise en forme des messages de réponse.|  
|`UriTemplate`|Spécifie le modèle URI qui contrôle quelles requêtes HTTP sont mappées à l'opération de service à laquelle l'attribut est appliqué.|  
  
## WebHttpBinding  
 La classe <xref:System.ServiceModel.WebHttpBinding> intègre une prise en charge des données XML, JSON et des données binaires brutes à l'aide de <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>.  Elle se compose d'un <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, d'un <xref:System.ServiceModel.Channels.HttpTransportBindingElement> et d'un objet <xref:System.ServiceModel.WebHttpSecurity>.  <xref:System.ServiceModel.WebHttpBinding> est conçu pour être utilisé en conjonction avec <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
## WebInvokeAttribute  
 L'attribut <xref:System.ServiceModel.Web.WebInvokeAttribute> est semblable au <xref:System.ServiceModel.Web.WebGetAttribute>, mais il est utilisé pour marquer une opération de service en tant qu'opération qui répond aux requêtes HTTP autres que GET.  Il s'agit d'un comportement d'opération passif \(les méthodes <xref:System.ServiceModel.Description.IOperationBehavior> n'ont aucune action\) qui ajoute des métadonnées à la description de l'opération.  L'attribut <xref:System.ServiceModel.Web.WebInvokeAttribute> n'a aucun effet à moins qu'un comportement recherchant ces métadonnées dans la description de l'opération \(en particulier <xref:System.ServiceModel.Description.WebHttpBehavior>\) soit ajouté à la collection de comportements du service.  
  
 L'attribut <xref:System.ServiceModel.Web.WebInvokeAttribute> accepte les paramètres optionnels indiqués dans le tableau suivant :  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`BodyStyle`|Contrôle si les demandes envoyées à l'opération de service à laquelle l'attribut est appliqué et les réponses reçues en retour doivent être encapsulées.|  
|`Method`|Spécifie la méthode HTTP à laquelle l'opération de service est mappée.|  
|`RequestFormat`|Contrôle la mise en forme des messages de demande.|  
|`ResponseFormat`|Contrôle la mise en forme des messages de réponse.|  
|`UriTemplate`|Spécifie le modèle URI qui contrôle quelles demandes GET sont mappées à l'opération de service à laquelle l'attribut est appliqué.|  
  
## UriTemplate  
 La classe <xref:System.UriTemplate> vous permet de définir un jeu d'URI de structure similaire.  Les modèles sont composés de deux parties : un chemin d'accès et une requête.  Un chemin d'accès est constitué d'une série de segments délimités par une barre oblique \(\/\).  Chaque segment peut avoir une valeur littérale, une valeur variable \(écrite entre accolades \[{}\], avec obligation de correspondre au contenu exact d'un segment\) ou un caractère générique \(un astérisque \[\*\] qui correspond au reste du chemin d'accès\).  L'expression de requête peut être entièrement omise.  Si elle est présente, elle spécifie une série non triée de paires nom\/valeur.  Les éléments de l'expression de requête peuvent être des paires littérales \(? x\=2\) ou des paires variables \(? x \= {*valeur*}\).  Les valeurs non couplées ne sont pas autorisées.  <xref:System.UriTemplate> est utilisé en interne par le modèle de programmation Web HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pour mapper des URI spécifiques ou des groupes d'URI aux opérations de service.  
  
## UriTemplateTable  
 La classe <xref:System.UriTemplateTable> représente un jeu associatif d'objets <xref:System.UriTemplate> liés à un objet choisi par le développeur.  Elle vous permet de faire correspondre les URI \(Uniform Resource Identifiers\) des candidats par rapport aux modèles du jeu et de récupérer les données associées aux modèles correspondants.  <xref:System.UriTemplateTable> est utilisé en interne par le modèle de programmation Web HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pour mapper des URI spécifiques ou des groupes d'URI aux opérations de service.  
  
## WebServiceHost  
 <xref:System.ServiceModel.Web.WebServiceHost> étend le <xref:System.ServiceModel.ServiceHost> de manière à faciliter l'hébergement d'un service de style Web non\-SOAP.  Si <xref:System.ServiceModel.Web.WebServiceHost> ne trouve aucun point de terminaison dans la description du service, il crée automatiquement un point de terminaison par défaut au niveau de l'adresse de base du service.  Lors de la création d'un point de terminaison HTTP par défaut, <xref:System.ServiceModel.Web.WebServiceHost> désactive également la page d'aide HTTP et la fonctionnalité WSDL \(Web Services Description Language\) GET afin que le point de terminaison des métadonnées n'interfère pas avec le point de terminaison HTTP par défaut.   <xref:System.ServiceModel.Web.WebServiceHost> garantit également que le <xref:System.ServiceModel.Description.WebHttpBehavior> requis soit attaché à tous les points de terminaison qui utilisent <xref:System.ServiceModel.WebHttpBinding>.  Enfin, <xref:System.ServiceModel.Web.WebServiceHost> configure automatiquement la liaison du point de terminaison afin qu'il puisse profiter des paramètres de sécurité IIS \(Internet Information Services\) en cas d'utilisation dans un répertoire virtuel sécurisé.  
  
## WebServiceHostFactory  
 La classe <xref:System.ServiceModel.Activation.WebServiceHostFactory> est utilisée pour créer dynamiquement un <xref:System.ServiceModel.Web.WebServiceHost> lorsqu'un service est hébergé dans les services IIS \(Internet Information Services\) ou WAS \(Windows Process Activation Service\).  À la différence d'un service auto\-hébergé où l'application d'hébergement instancie le <xref:System.ServiceModel.Web.WebServiceHost>, les services hébergés dans les services IIS ou WAS utilisent cette classe pour créer le <xref:System.ServiceModel.Web.WebServiceHost> pour ces services.  La méthode [CreateServiceHost\(Type, Uri\<xref:System.ServiceModel.Activation.WebServiceHostFactory.CreateServiceHost%28System.Type%2CSystem.Uri%5B%5D%29> est appelée lorsqu'une demande entrante pour le service est reçue.  
  
## WebHttpBehavior  
 La classe <xref:System.ServiceModel.Description.WebHttpBehavior> fournit les formateurs, sélecteurs d'opération, etc. requis pour la prise en charge de service de style Web au niveau de la couche de modèle de service.  Il est implémenté en tant que comportement de point de terminaison \(utilisé en conjonction avec <xref:System.ServiceModel.WebHttpBinding>\) et autorise la spécification de formateurs et de sélecteurs d'opération pour chaque point de terminaison, ce qui permet à une même implémentation de service d'exposer à la fois des points de terminaison SOAP et POX.  
  
### Extension de WebHttpBehavior  
 <xref:System.ServiceModel.Description.WebHttpBehavior> peut être étendu à l'aide de différentes méthodes virtuelles : <xref:System.ServiceModel.Description.WebHttpBehavior.GetOperationSelector%28System.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetReplyClientFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetRequestClientFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetReplyDispatchFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29> et <xref:System.ServiceModel.Description.WebHttpBehavior.GetRequestDispatchFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>.  Les développeurs peuvent dériver une classe de <xref:System.ServiceModel.Description.WebHttpBehavior> et substituer ces méthodes de manière à personnaliser le comportement par défaut.  
  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> est un exemple d'extension de <xref:System.ServiceModel.Description.WebHttpBehavior>.  <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> permet aux points de terminaison [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] de recevoir des requêtes HTTP provenant d'un client AJAX ASP.NET basé sur un navigateur.  Le [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) est un exemple de l'utilisation de ce point d'extensibilité.  
  
> [!WARNING]
>  Lors de l'utilisation de <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>, <xref:System.UriTemplate> ne sont pas pris en charge dans les attributs <xref:System.ServiceModel.Web.WebGetAttribute> ou <xref:System.ServiceModel.Web.WebInvokeAttribute>.  
  
## WebHttpDispatchOperationSelector  
 La classe <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector> utilise les classes <xref:System.UriTemplate> et <xref:System.UriTemplateTable> pour distribuer les appels aux opérations de service.  
  
## Compatibilité  
 Le modèle de programmation Web HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] n'utilise pas de messages SOAP et par conséquent ne prend pas en charge les protocoles WS\-\*.  Vous pouvez toutefois exposer le même contrat par deux points de terminaison différents, l'un utilisant SOAP et l'autre pas.  Pour obtenir un exemple, consultez [Comment : exposer un contrat à des clients SOAP et Web](../../../../docs/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md).  
  
## Sécurité  
 Comme le modèle de programmation Web HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ne prend pas en charge les protocoles WS\-\*, la seule manière de sécuriser un service Web reposant sur le modèle de programmation Web HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste à exposer votre service avec SSL.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la configuration de SSL avec [!INCLUDE[iisver](../../../../includes/iisver-md.md)], consultez [Comment implémenter SSL dans IIS](http://go.microsoft.com/fwlink/?LinkId=131613)  
  
## Voir aussi  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Web.WebGetAttribute>   
 <xref:System.ServiceModel.Web.WebInvokeAttribute>   
 <xref:System.ServiceModel.Description.WebHttpBehavior>   
 <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>   
 [Vue d'ensemble du modèle de programmation Web HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)