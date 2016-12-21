---
title: "HString::MakeReference 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference"
dev_langs: 
  - "C++"
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::MakeReference 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 문자열 매개 변수에서 HStringReference 개체를 만듭니다.  
  
## 구문  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
#### 매개 변수  
 `sizeDest`  
 HStringReference 대상 버퍼의 크기를 지정 하는 템플릿 매개 변수입니다.  
  
 `str`  
 와이드 문자열에 대한 참조입니다.  
  
 `len`  
 `str` 매개변수의 최대 길이는 이 작업에서 사용하기 위한 버퍼입니다.  `len` 매개변수가 지정되지 않은 경우, 전체 `str` 매개변수가 사용됩니다.  
  
## 반환 값  
 개체 값이 지정 된 동일한 HStringReference `str` 매개 변수입니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)