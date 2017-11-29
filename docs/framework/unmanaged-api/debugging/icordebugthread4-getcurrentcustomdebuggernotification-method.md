---
title: "ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd865e720e4ed938cf1634ebe5f1c324c4c3256e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="f7036-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="f7036-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>
<span data-ttu-id="f7036-103">현재 가져옵니다 [icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 현재 스레드에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f7036-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7036-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7036-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCustomDebuggerNotification(  
    [out] ICorDebugValue **ppNotificationObject  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7036-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7036-105">Parameters</span></span>  
 `ppNOtificationObject`  
 <span data-ttu-id="f7036-106">[out] 현재에 대 한 포인터 `ICorDebugManagedCallback3::CustomNotification` 현재 스레드에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f7036-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7036-107">설명</span><span class="sxs-lookup"><span data-stu-id="f7036-107">Remarks</span></span>  
 <span data-ttu-id="f7036-108">값 `ppNotificationObject` 메서드 내에서 호출 되지 않으면 null을 `ICorDebugManagedCallback3::CustomNotification` 콜백을 현재 알림 개체가 없는 경우 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7036-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7036-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7036-109">Requirements</span></span>  
 <span data-ttu-id="f7036-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7036-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7036-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7036-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7036-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7036-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7036-113">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7036-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7036-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7036-114">See Also</span></span>  
 [<span data-ttu-id="f7036-115">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7036-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="f7036-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7036-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f7036-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="f7036-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)