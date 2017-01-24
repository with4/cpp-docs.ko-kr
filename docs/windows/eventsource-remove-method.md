---
title: "EventSource::Remove 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::Remove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Remove 메서드"
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::Remove 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 EventSource 개체에 연결 된 이벤트 처리기의 집합에서 지정 된 이벤트 등록 토큰이 나타내는 이벤트 처리기를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `token`  
 이벤트 처리기를 나타내는 핸들입니다. 이 토큰으로 이벤트 처리기가 등록 될 때 반환 된는 [add ()](../windows/eventsource-add-method.md) 메서드.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 EventRegistrationToken 구조에 대 한 자세한 내용은 Windows 런타임 참조 설명서에서 Windows::Foundation::EventRegistrationToken 구조 항목을 참조 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [EventSource 클래스](../windows/eventsource-class.md)