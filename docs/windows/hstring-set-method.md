---
title: "HString::Set 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::Set"
dev_langs: 
  - "C++"
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# HString::Set 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 HString 개체의 값을 지정된 와이드 문자 문자열 또는 HString 매개 변수로 설정합니다.  
  
## 구문  
  
```  
  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
#### 매개 변수  
 `str`  
 넓은 문자 문자열입니다.  
  
 `len`  
 현재 HString 개체에 할당하는 `str` 매개변수의 최대길이 입니다.  
  
 `hstr`  
 기존 HString 개체  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)