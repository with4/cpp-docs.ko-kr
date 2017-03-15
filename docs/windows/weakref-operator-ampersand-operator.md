---
title: "WeakRef::operator&amp; 연산자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator& 연산자"
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::operator&amp; 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 WeakRef 객체를 나타내는 ComPtrRef 개체를 반환 합니다.  
  
## 구문  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## 반환 값  
 현재 WeakRef 객체를 나타내는 ComPtrRef 개체를 반환 합니다.  
  
## 설명  
 이것은 내부 도우미 연산자를 코드에 사용할 수 없습니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)