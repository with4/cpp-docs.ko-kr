---
title: 'Asyncbase:: Trytransitiontoerror 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc677304ae7ab61e6726366869e85f731cd92484
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463209"
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
 *error*  
 HRESULT 오류가 발생 합니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 내부 오류 상태가 고, 그렇지 않으면 변경 되었으면 **false**합니다.  
  
## <a name="remarks"></a>설명  
 오류 상태는 s_ok가 이미 설정 되어 있는 경우에이 작업은 오류 상태를 수정 합니다. 이 작업이 오류 상태가 이미 오류, 취소, 완료 또는 종료 하는 경우에 효과가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)