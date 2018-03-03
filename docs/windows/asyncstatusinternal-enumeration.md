---
title: "AsyncStatusInternal 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd277fecb0bc63d5ee823af98df8aa298b285964
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 열거형
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>설명  
 비동기 작업의 상태에 대 한 내부 열거형 간의 매핑을 지정 및 **Windows::Foundation::AsyncStatus** 열거 합니다.  
  
## <a name="members"></a>멤버  
 `_Created`  
 에 해당:: Windows::Foundation::AsyncStatus:: 생성  
  
 `_Started`  
 에 해당:: Windows::Foundation::AsyncStatus:: 시작  
  
 `_Completed`  
 에 해당:: Windows::Foundation::AsyncStatus:: 완료  
  
 `_Cancelled`  
 에 해당:: Windows::Foundation::AsyncStatus:: 취소  
  
 `_Error`  
 에 해당:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)