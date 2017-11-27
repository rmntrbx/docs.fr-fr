---
title: "CorDebugExceptionFlags, énumération"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionFlags
helpviewer_keywords: CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35444a73a5d3b5d71a1aa991dbebc3e7da705292
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="9b752-102">CorDebugExceptionFlags, énumération</span><span class="sxs-lookup"><span data-stu-id="9b752-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="9b752-103">Fournit des informations supplémentaires sur une exception.</span><span class="sxs-lookup"><span data-stu-id="9b752-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b752-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9b752-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9b752-105">Membres</span><span class="sxs-lookup"><span data-stu-id="9b752-105">Members</span></span>  
  
|<span data-ttu-id="9b752-106">Membre</span><span class="sxs-lookup"><span data-stu-id="9b752-106">Member</span></span>|<span data-ttu-id="9b752-107">Description</span><span class="sxs-lookup"><span data-stu-id="9b752-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="9b752-108">Il n'existe pas d'exception.</span><span class="sxs-lookup"><span data-stu-id="9b752-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="9b752-109">L'exception peut être interceptée.</span><span class="sxs-lookup"><span data-stu-id="9b752-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="9b752-110">Le moment où se produit l'exception peut néanmoins être tel que le débogueur ne peut pas l'intercepter.</span><span class="sxs-lookup"><span data-stu-id="9b752-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="9b752-111">Par exemple, s'il n'existe pas de code managé en dessous du rappel actif ou si l'événement d'exception provient d'un attachement juste-à-temps, l'exception ne peut pas être interceptée.</span><span class="sxs-lookup"><span data-stu-id="9b752-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b752-112">Remarques</span><span class="sxs-lookup"><span data-stu-id="9b752-112">Remarks</span></span>  
 <span data-ttu-id="9b752-113">De nouvelles valeurs sont susceptibles d'être ajoutées dans les versions ultérieures : il est donc recommandé de préparer du code qui utilise `CorDebugExceptionFlags` pour les valeurs inattendues.</span><span class="sxs-lookup"><span data-stu-id="9b752-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b752-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="9b752-114">Requirements</span></span>  
 <span data-ttu-id="9b752-115">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b752-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b752-116">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b752-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b752-117">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b752-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b752-118">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b752-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b752-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b752-119">See Also</span></span>  
 [<span data-ttu-id="9b752-120">Énumérations de débogage</span><span class="sxs-lookup"><span data-stu-id="9b752-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)