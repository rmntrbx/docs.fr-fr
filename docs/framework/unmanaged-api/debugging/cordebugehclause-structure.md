---
title: CorDebugEHClause, structure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugEHClause
api_location: mscordbi.dll
api_type: COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 154bbe14a14d34c0d998e3192a70a96b9922f32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="7be8d-102">CorDebugEHClause, structure</span><span class="sxs-lookup"><span data-stu-id="7be8d-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="7be8d-103">[Pris en charge dans .NET Framework 4.5.2 et ultérieur]</span><span class="sxs-lookup"><span data-stu-id="7be8d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7be8d-104">Représente une clause de gestion des exceptions pour un bloc spécifié de code de langage intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="7be8d-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be8d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7be8d-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="7be8d-106">Membres</span><span class="sxs-lookup"><span data-stu-id="7be8d-106">Members</span></span>  
  
|<span data-ttu-id="7be8d-107">Membre</span><span class="sxs-lookup"><span data-stu-id="7be8d-107">Member</span></span>|<span data-ttu-id="7be8d-108">Description</span><span class="sxs-lookup"><span data-stu-id="7be8d-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="7be8d-109">Un champ de bits qui décrit les informations de l'exception dans la clause de gestion des exceptions.</span><span class="sxs-lookup"><span data-stu-id="7be8d-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="7be8d-110">Pour plus d'informations, consultez la section Remarques.</span><span class="sxs-lookup"><span data-stu-id="7be8d-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="7be8d-111">Le décalage en octets du bloc `try` à partir du début du corps de la méthode.</span><span class="sxs-lookup"><span data-stu-id="7be8d-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="7be8d-112">La longueur en octets du bloc `try`.</span><span class="sxs-lookup"><span data-stu-id="7be8d-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="7be8d-113">L'emplacement du gestionnaire pour ce bloc `try`.</span><span class="sxs-lookup"><span data-stu-id="7be8d-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="7be8d-114">La taille du code du gestionnaire en octets.</span><span class="sxs-lookup"><span data-stu-id="7be8d-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="7be8d-115">Le jeton de métadonnées pour un gestionnaire d'exceptions basé sur les types.</span><span class="sxs-lookup"><span data-stu-id="7be8d-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="7be8d-116">Le décalage en octets depuis le début du corps de la méthode pour un gestionnaire d'exceptions basé sur les filtres.</span><span class="sxs-lookup"><span data-stu-id="7be8d-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7be8d-117">Remarques</span><span class="sxs-lookup"><span data-stu-id="7be8d-117">Remarks</span></span>  
 <span data-ttu-id="7be8d-118">Un tableau de `CoreDebugEHClause` valeurs est retourné par la [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="7be8d-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="7be8d-119">Les informations de la clause du gestionnaire d'exceptions sont définies par la spécification CLI.</span><span class="sxs-lookup"><span data-stu-id="7be8d-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="7be8d-120">Pour plus d’informations, consultez [Standard ECMA-355 : Common Language Infrastructure (CLI), 6th Edition](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="7be8d-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="7be8d-121">Le champ `flags` peut contenir les indicateurs suivants.</span><span class="sxs-lookup"><span data-stu-id="7be8d-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="7be8d-122">Notez qu'ils ne sont pas définis dans CorDebug.idl ou CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="7be8d-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="7be8d-123">Indicateur</span><span class="sxs-lookup"><span data-stu-id="7be8d-123">Flag</span></span>|<span data-ttu-id="7be8d-124">Valeur</span><span class="sxs-lookup"><span data-stu-id="7be8d-124">Value</span></span>|<span data-ttu-id="7be8d-125">Description</span><span class="sxs-lookup"><span data-stu-id="7be8d-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="7be8d-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="7be8d-126">0x00000000</span></span>|<span data-ttu-id="7be8d-127">Une clause d'exception typée.</span><span class="sxs-lookup"><span data-stu-id="7be8d-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="7be8d-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="7be8d-128">0x00000001</span></span>|<span data-ttu-id="7be8d-129">Une clause de filtre et de gestionnaire d'exceptions.</span><span class="sxs-lookup"><span data-stu-id="7be8d-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="7be8d-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="7be8d-130">0x00000002</span></span>|<span data-ttu-id="7be8d-131">Une clause `finally`.</span><span class="sxs-lookup"><span data-stu-id="7be8d-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="7be8d-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="7be8d-132">0x00000004</span></span>|<span data-ttu-id="7be8d-133">Une clause fault (une clause `finally` qui est appelée seulement quand une exception est levée).</span><span class="sxs-lookup"><span data-stu-id="7be8d-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7be8d-134">Spécifications</span><span class="sxs-lookup"><span data-stu-id="7be8d-134">Requirements</span></span>  
 <span data-ttu-id="7be8d-135">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be8d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be8d-136">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7be8d-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7be8d-137">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be8d-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be8d-138">**Versions du .NET framework :**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be8d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be8d-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7be8d-139">See Also</span></span>  
 [<span data-ttu-id="7be8d-140">Getehclauses, méthode</span><span class="sxs-lookup"><span data-stu-id="7be8d-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)  
 [<span data-ttu-id="7be8d-141">Structures de débogage</span><span class="sxs-lookup"><span data-stu-id="7be8d-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)