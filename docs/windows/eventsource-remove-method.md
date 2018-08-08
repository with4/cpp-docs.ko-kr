---
title: 'Eventsource:: Remove 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9dd026158a2bbc76e7a3e195bc5346f65821f2b7
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569497"
---
# <a name="eventsourceremove-method"></a>EventSource::Remove 메서드
현재 연결 된 이벤트 처리기 집합에서 지정 된 이벤트 등록 토큰을 나타내는 이벤트 처리기를 삭제 **EventSource** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *token*  
 이벤트 처리기를 나타내는 핸들입니다. 이 토큰은 이벤트 처리기를 등록 된 경우 반환 된 합니다 [add ()](../windows/eventsource-add-method.md) 메서드.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 EventRegistrationToken 구조체에 대 한 자세한 내용은 참조는 `Windows::Foundation::EventRegistrationToken` Windows 런타임 참조 문서의 구조 항목입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [EventSource 클래스](../windows/eventsource-class.md)