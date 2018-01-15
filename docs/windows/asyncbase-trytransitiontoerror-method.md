---
title: "Asyncbase:: Trytransitiontoerror 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs: C++
helpviewer_keywords: TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6da3d84e3e5e1ee0fd71da1cf59ec79497f81d35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError 메서드
지정된 된 오류 코드 내부 오류 상태를 수정할 수 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `error`  
 오류 HRESULT입니다.  
  
## <a name="return-value"></a>반환 값  
 `true`내부 오류 상태가 변경 되었습니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 오류 상태 S_OK를 이미 설정한 경우에이 작업은 오류 상태를 수정 합니다. 오류 상태는 이미 오류, 취소, 완료 또는 종료 하는 경우이 작업은 효과가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)