---
title: "ComPtr::ComPtr 생성자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr, 생성자"
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::ComPtr 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ComPtr 클래스의 새 인스턴스를 초기화합니다.  기본, 복사, 이동 및 변환 생성자 오버 로드를 제공 합니다.  
  
## 구문  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### 매개 변수  
 `U`  
 `other` 매개 변수의 형식입니다.  
  
 `other`  
 `U` 형식의 개체입니다.  
  
## 반환 값  
  
## 설명  
 첫 번째 생성자는 변환이 가능한 빈 개체를 만드는 기본생성자 입니다.  두 번째 생성자는 [\_nullptr](../windows/nullptr-cpp-component-extensions.md) 을 지정합니다. 이는 직접적으로 빈 개체를 만듭니다.  
  
 세 번째 생성자는 포인터로 지정한 개체에서 개체를 만듭니다.  
  
 네 번째 및 다섯 번째 생성자는 복사 생성자입니다.  다섯 번째 생성자는 현재 형식으로 변환할 수 있으면 개체를 복사 합니다.  
  
 여섯 번째 및 일곱 번째 생성자는 move 생성자입니다.  일곱 번째 생성자 현재 형식으로 변환할 수 있으면 개체를 이동 합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)