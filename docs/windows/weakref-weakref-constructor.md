---
title: "WeakRef::WeakRef 생성자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef, 생성자"
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::WeakRef 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WeakRef 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### 매개 변수  
 `ptr`  
 포인터, 참조, 또는 현재 WeakRef 객체를 초기화 하는 기존 개체에 rvalue 참조합니다.  
  
## 설명  
 첫 번째 생성자는 빈 WeakRef 객체를 초기화합니다.  두 번째 생성자는 IWeakReference 인터페이스에 대 한 포인터에서 WeakRef 객체를 초기화합니다.  세 번째 생성자는 ComPtr에 대한 참조에서 WeakRef 객체\< IWeakReference\> 개체입니다.  네 번째 및 다섯 번째 생성자에서 다른 WeakRef 객체 WeakRef 개체를 초기화 합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)