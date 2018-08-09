---
title: 'Asyncbase:: Get_status 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Status
dev_langs:
- C++
helpviewer_keywords:
- get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b49e7cbd30445250bdf0710973ba65e47823b36c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652255"
---
# <a name="asyncbasegetstatus-method"></a>AsyncBase::get_Status 메서드
비동기 작업의 상태를 나타내는 값을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHOD(  
   get_Status  
)(AsyncStatus *status) override;  
```  
  
### <a name="parameters"></a>매개 변수  
 *status*  
 상태를 저장할 위치입니다. 자세한 내용은 참조 하세요. `Windows::Foundation::AsyncStatus` 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 E_ILLEGAL_METHOD_CALL 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 `IAsyncInfo::get_Status`를 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)