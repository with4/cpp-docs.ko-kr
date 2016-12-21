---
title: "HStringReference::CopyTo 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::CopyTo 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 HStringReference 개체를 HSTRING 개체로 복사합니다.  
  
## 구문  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### 매개 변수  
 `str`  
 복사본을 받는 HSTRING입니다.  
  
## 설명  
 이 메서드는 [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) 함수를 호출합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)