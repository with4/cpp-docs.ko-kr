---
title: CancelTransitionPolicy 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64f588e67066fed690271aa7d78fcbe726c67177
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy 열거형
종료 상태를 전환 하는 비동기 작업의 시도 하는 방법을 나타냅니다 완료 또는 오류는 클라이언트 요청 취소 된 상태에 대해 작동 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum CancelTransitionPolicy;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`RemainCanceled`|비동기 작업을 현재 클라이언트 요청 취소 된 상태에 있을 경우이 달리 터미널 완료 또는 오류 상태로 전환 되 고 취소 된 상태로 계속 유지 됩니다을 나타냅니다.|  
|`TransitionFromCanceled`|취소 된 상태로 터미널 상태에 완료 된 상태로 전환 되어야 나타냅니다 비동기 작업을 현재 클라이언트 요청 취소 된 상태에 있을 경우 또는이 플래그를 활용 하는 호출에 의해 결정 된 대로 오류입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)