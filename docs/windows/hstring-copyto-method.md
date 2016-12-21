---
title: "HString::CopyTo 메서드 | Microsoft Docs"
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
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::CopyTo 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 HString 개체를 HSTRING 개체로 복사합니다.  
  
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
 [HString 클래스](../windows/hstring-class.md)