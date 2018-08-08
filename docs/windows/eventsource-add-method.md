---
title: 'Eventsource:: Add 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Add
dev_langs:
- C++
helpviewer_keywords:
- Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90750f965768d5ecda40e074f9a136407613d2d2
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570391"
---
# <a name="eventsourceadd-method"></a>EventSource::Add 메서드
현재 이벤트 처리기 집합에 지정 된 대리자를 인터페이스에 의해 표시 되는 이벤트 처리기 추가 **EventSource** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *delegateInterface*  
 이벤트 처리기를 나타내는 대리자 개체에 대 한 인터페이스입니다.  
  
 *token*  
 이 작업이 완료 될 때 이벤트를 나타내는 핸들입니다. 이 토큰에 대 한 매개 변수로 사용 합니다 [remove ()](../windows/eventsource-remove-method.md) 이벤트 처리기를 삭제 하는 방법입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [EventSource 클래스](../windows/eventsource-class.md)