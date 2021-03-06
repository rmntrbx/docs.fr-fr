---
title: "IHostThreadPoolManager::GetMaxThreads, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 84867f1b5dfdcfd7a50d01c9e51cb0c42da62f0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>IHostThreadPoolManager::GetMaxThreads, méthode
Obtient le nombre maximal de threads que l’hôte conserve simultanément dans le pool de threads.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pdwMaxWorkerThreads`  
 [out] Pointeur vers le nombre maximal de threads que l’hôte gère dans le pool de threads.  
  
## <a name="return-value"></a>Valeur de retour  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads`retourné avec succès.|  
|HOST_E_CLRNOTAVAILABLE|Le common language runtime (CLR (n’a pas été chargé dans un processus, ou le CLR est dans un état dans lequel elle ne peut pas exécuter le code managé ou un processus l’appel avec succès.|  
|HOST_E_TIMEOUT|L’appel a expiré.|  
|HOST_E_NOT_OWNER|L’appelant ne possède pas le verrou.|  
|HOST_E_ABANDONED|Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.|  
|E_FAIL|Une défaillance grave et inconnue s’est produite. Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus. Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L’hôte ne fournit pas une implémentation de `GetMaxThreads`.|  
  
## <a name="remarks"></a>Notes  
 Le CLR appelle `GetMaxThreads` pour déterminer le nombre total de threads dans le pool de threads. Le [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) méthode obtient le nombre de threads qui ne traitent pas actuellement des éléments de travail. Toutes les demandes supérieures à la valeur retournée de la `pdwMaxWorkerThreads` paramètre restent en file d’attente jusqu'à ce que les threads deviennent disponibles.  
  
 Si l’hôte ne fournit pas une implémentation de `GetMaxThreads`, elle doit retourner une valeur HRESULT d’E_NOTIMPL.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [GetMinThreads, méthode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [SetMaxThreads, méthode](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [IHostThreadPoolManager, interface](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
