---
title: "HStringReference::HStringReference 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# HStringReference::HStringReference 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HStringReference 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest],   
unsigned int len)  
       throw();  
  
    HStringReference(HStringReference&& other) throw();  
  
```  
  
#### 매개 변수  
 `sizeDest`  
 HStringReference 대상 버퍼의 크기를 지정 하는 템플릿 매개 변수입니다.  
  
 `str`  
 와이드 문자열에 대한 참조입니다.  
  
 `len`  
 `str` 매개변수의 최대 길이는 이 작업에서 사용하기 위한 버퍼입니다.  `len` 매개변수가 지정되지 않은 경우, 전체 `str` 매개변수가 사용됩니다.  만일 `len` 가 `sizeDest` 보다 큰 경우, `len` 은 `sizeDest` \-1 로 설정합니다.  
  
 `other`  
 다른 HStringReference 개체입니다.  
  
## 설명  
 첫 번째 생성자는 매개변수 `str` 과 동일한 크기인 새로운 HString참조 개체를 초기화합니다.  
  
 두 번째 생성자는 매개변수 `len` 로 지정된 크기의 새로운 HString참조 개체를 초기화합니다.  
  
 세 번째 생성자는 `other` 매개변수의 값에 대한 새로운 HString참조 개체를 초기화하고 그때, `other` 매개변수를 삭제합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)