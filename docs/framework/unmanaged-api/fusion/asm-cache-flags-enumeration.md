---
title: "ASM_CACHE_FLAGS, énumération"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASM_CACHE_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: ASM_CACHE_FLAGS
helpviewer_keywords: ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 767cae15c37b8c62d47085533ea9fa3ce4957963
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="c3f92-102">ASM_CACHE_FLAGS, énumération</span><span class="sxs-lookup"><span data-stu-id="c3f92-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="c3f92-103">Indique la source d’un assembly qui est représenté par [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) dans le global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="c3f92-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3f92-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c3f92-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c3f92-105">Membres</span><span class="sxs-lookup"><span data-stu-id="c3f92-105">Members</span></span>  
  
|<span data-ttu-id="c3f92-106">Membre</span><span class="sxs-lookup"><span data-stu-id="c3f92-106">Member</span></span>|<span data-ttu-id="c3f92-107">Description</span><span class="sxs-lookup"><span data-stu-id="c3f92-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="c3f92-108">Énumère le cache d’assemblys précompilés à l’aide de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="c3f92-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="c3f92-109">Énumère le global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="c3f92-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="c3f92-110">Énumère les assemblys qui ont été téléchargées à la demande ou qui ont été cliché instantané.</span><span class="sxs-lookup"><span data-stu-id="c3f92-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="c3f92-111">Indique que le [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) fonction doit retourner le chemin d’accès dans le global assembly cache pour le common language runtime (CLR) version 2.0.</span><span class="sxs-lookup"><span data-stu-id="c3f92-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="c3f92-112">Pertinent uniquement dans le contexte d’un appel à [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="c3f92-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="c3f92-113">Indique que le [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) fonction doit retourner le chemin d’accès au global assembly cache pour le CLR version 4.</span><span class="sxs-lookup"><span data-stu-id="c3f92-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="c3f92-114">Pertinent uniquement dans le contexte d’un appel à [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="c3f92-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3f92-115">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c3f92-115">Requirements</span></span>  
 <span data-ttu-id="c3f92-116">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3f92-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3f92-117">**En-tête :** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c3f92-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c3f92-118">**Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3f92-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3f92-119">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3f92-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f92-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3f92-120">See Also</span></span>  
 [<span data-ttu-id="c3f92-121">GetCachePath (fonction)</span><span class="sxs-lookup"><span data-stu-id="c3f92-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="c3f92-122">IAssemblyCacheItem (Interface)</span><span class="sxs-lookup"><span data-stu-id="c3f92-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="c3f92-123">Énumérations de fusion</span><span class="sxs-lookup"><span data-stu-id="c3f92-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)