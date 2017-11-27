---
title: StrongNameSignatureVerification, fonction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerification
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerification
helpviewer_keywords: StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2c04aba5b774b299e26be8dc532b894b6c6fad5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="138f2-102">StrongNameSignatureVerification, fonction</span><span class="sxs-lookup"><span data-stu-id="138f2-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="138f2-103">Obtient une valeur qui indique si le manifeste d’assembly dans le chemin d’accès fourni contient une signature de nom fort, qui est vérifiée en fonction des indicateurs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="138f2-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="138f2-104">Cette fonction est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="138f2-104">This function has been deprecated.</span></span> <span data-ttu-id="138f2-105">Utilisez le [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) méthode à la place.</span><span class="sxs-lookup"><span data-stu-id="138f2-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138f2-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="138f2-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="138f2-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="138f2-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="138f2-108">[in] Le chemin d’accès pour le fichier exécutable portable (.dll ou .exe) pour l’assembly à vérifier.</span><span class="sxs-lookup"><span data-stu-id="138f2-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="138f2-109">[in] Indicateurs pour modifier le comportement de vérification.</span><span class="sxs-lookup"><span data-stu-id="138f2-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="138f2-110">Les valeurs suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="138f2-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="138f2-111">`SN_INFLAG_FORCE_VER`(0 x 00000001) - force la vérification même s’il est nécessaire de remplacer les paramètres du Registre.</span><span class="sxs-lookup"><span data-stu-id="138f2-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="138f2-112">`SN_INFLAG_INSTALL`(0 x 00000002) - Spécifie qu’il s’agit de la première fois que le manifeste est vérifié.</span><span class="sxs-lookup"><span data-stu-id="138f2-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="138f2-113">`SN_INFLAG_ADMIN_ACCESS`(0 x 00000004) - Spécifie que le cache autorise l’accès uniquement aux utilisateurs qui ont des privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="138f2-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="138f2-114">`SN_INFLAG_USER_ACCESS`(0 x 00000008) - Spécifie que l’assembly est accessible uniquement à l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="138f2-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="138f2-115">`SN_INFLAG_ALL_ACCESS`(0 x 00000010) - Spécifie que le cache ne va fournir aucune garantie de restriction d’accès.</span><span class="sxs-lookup"><span data-stu-id="138f2-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="138f2-116">`SN_INFLAG_RUNTIME`(0 x 80000000) - réservé pour le débogage interne.</span><span class="sxs-lookup"><span data-stu-id="138f2-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="138f2-117">[out] Indicateurs qui indique si la signature de nom fort a été vérifiée.</span><span class="sxs-lookup"><span data-stu-id="138f2-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="138f2-118">La valeur suivante est prise en charge :</span><span class="sxs-lookup"><span data-stu-id="138f2-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="138f2-119">`SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001) - cette valeur est définie sur `false` pour spécifier que la vérification a réussi en raison des paramètres de Registre.</span><span class="sxs-lookup"><span data-stu-id="138f2-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="138f2-120">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="138f2-120">Return Value</span></span>  
 <span data-ttu-id="138f2-121">`true`Si la vérification a réussi ; dans le cas contraire, `false`.</span><span class="sxs-lookup"><span data-stu-id="138f2-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="138f2-122">Spécifications</span><span class="sxs-lookup"><span data-stu-id="138f2-122">Requirements</span></span>  
 <span data-ttu-id="138f2-123">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="138f2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="138f2-124">**En-tête :** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="138f2-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="138f2-125">**Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="138f2-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="138f2-126">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="138f2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138f2-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="138f2-127">See Also</span></span>  
 [<span data-ttu-id="138f2-128">StrongNameSignatureVerification (méthode)</span><span class="sxs-lookup"><span data-stu-id="138f2-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="138f2-129">StrongNameSignatureVerificationEx (méthode)</span><span class="sxs-lookup"><span data-stu-id="138f2-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="138f2-130">ICLRStrongName Interface</span><span class="sxs-lookup"><span data-stu-id="138f2-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)