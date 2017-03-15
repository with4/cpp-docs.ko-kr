---
title: "WeakRef::As 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As 메서드"
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# WeakRef::As 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스를 나타내도록 지정된 ComPtr 포인터 매개 변수를 설정합니다.  
  
## 구문  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### 매개 변수  
 `U`  
 인터페이스 ID입니다.  
  
 `ptr`  
 이 작업이 완료되었을 때 `U` 매개 변수를 나타내는 개체입니다.  
  
## 반환 값  
  
-   이 작업이 성공하면 S\_OK이고, 실패하면 작업이 실패한 원인을 나타내는 HRESULT입니다. 그리고 `ptr`이 `nullptr`로 설정됩니다.  
  
-   이 작업이 성공하면 S\_OK이지만, 현재 WeakRef 개체는 이미 해제되었습니다.`ptr` 매개 변수가 `nullptr`로 설정됩니다.  
  
-   이 작업이 성공하면 S\_OK이지만, 현재 WeakRef 개체가 `U` 매개 변수에서 파생되지 않습니다.`ptr` 매개 변수가 `nullptr`로 설정됩니다.  
  
## 설명  
 `U` 매개 변수가 IWeakReference이거나 IInspectable에서 파생되지 않은 경우 오류가 발생합니다.  
  
 첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C\+\+ 언어 기능을 지원하는 내부 도우미 특수화입니다.  
  
 Windows 10 SDK부터는 약한 참조를 가져올 수 없는 경우 이 메서드에서 WeakRef 인스턴스를 `nullptr`로 설정하지 않으므로 WeakRef에서 `nullptr`을 검사하는 오류 검사 코드를 사용하지 않아야 합니다. 대신 메서드가 성공했는지 확인하려면 반환된 HRESULT를 검사하거나 `nullptr`에서 `ptr`를 검사합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)