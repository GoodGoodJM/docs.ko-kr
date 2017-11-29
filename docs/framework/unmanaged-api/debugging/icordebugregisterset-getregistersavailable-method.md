---
title: "ICorDebugRegisterSet::GetRegistersAvailable 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa4dd904b07aa2c9157e61e6968e96ef797ad3f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="0b543-102">ICorDebugRegisterSet::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="0b543-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="0b543-103">비트 마스크를 가져옵니다가 있는 레지스터를 나타내는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b543-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b543-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b543-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b543-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b543-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="0b543-106">[out] 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="0b543-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b543-107">설명</span><span class="sxs-lookup"><span data-stu-id="0b543-107">Remarks</span></span>  
 <span data-ttu-id="0b543-108">레지스터 주어진된 상황에 대 한 해당 값을 확인할 수 없는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b543-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="0b543-109">반환 된 마스크에는 각 레지스터에 대해 하나의 비트가 포함 (1 << 레지스터 인덱스).</span><span class="sxs-lookup"><span data-stu-id="0b543-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="0b543-110">레지스터를 사용할 수 있는 경우 비트 값이 1 또는 사용할 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0b543-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b543-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b543-111">Requirements</span></span>  
 <span data-ttu-id="0b543-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b543-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b543-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b543-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b543-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b543-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b543-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b543-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b543-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b543-116">See Also</span></span>  
 [<span data-ttu-id="0b543-117">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b543-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="0b543-118">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b543-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)