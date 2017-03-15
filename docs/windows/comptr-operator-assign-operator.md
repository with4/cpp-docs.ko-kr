---
title: "ComPtr::operator= 연산자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 연산자"
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 ComPtr에 값을 할당 합니다.  
  
## 구문  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### 매개 변수  
 `U`  
 A 클래스  
  
 `other`  
 포인터나 참조가 rvalue 참조 형식 또는 다른 ComPtr입니다.  
  
## 반환 값  
 현재 Compt에 대한 참조입니다.  
  
## 설명  
 이 연산자의 첫 번째 버전은 현재 ComPtr에 값을 할당합니다.  
  
 두 번째 버전을 할당 하는 인터페이스 포인터는 현재 ComPtr 인터페이스 포인터를 경우 현재 ComPtr에 두 번째 인터페이스 포인터 할당 됩니다.  
  
 세 번째 버전에서 할당 인터페이스 포인터는 현재 ComPtr에 할당 됩니다.  
  
 네 번째 버전을 할당 하는 값의 인터페이스 포인터는 현재 ComPtr 인터페이스 포인터를 경우 현재 ComPtr에 두 번째 인터페이스 포인터 할당 됩니다.  
  
 다섯 번째 버전은 복사 연산자입니다. 현재 ComPtr는 ComPtr에 대 한 참조 할당 됩니다.  
  
 여섯 번째 버전은 복사 연산자를 사용하는 이동을 의미합니다. rvalue 참조를 캐스팅하고 현재 ComPtr에 할당된 다음 형식은 정적이면 ComPtr입니다.  
  
 일곱 번째 버전은 복사 연산자를 사용하는 이동을 의미합니다. rvalue 참조를 현재 `U`형식의 ComPtr에 캐스팅하고 현재 ComPtr을 할당합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)