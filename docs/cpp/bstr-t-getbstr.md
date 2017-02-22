---
title: "_bstr_t::GetBSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "GetBSTR"
  - "_bstr_t::GetBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBSTR 메서드"
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::GetBSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_bstr_t`에 의해 래핑되는 `BSTR`의 시작 부분을 가리킵니다.  
  
## 구문  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## 반환 값  
 `_bstr_t`에 의해 래핑되는 `BSTR`의 시작 부분입니다.  
  
## 설명  
 `GetBSTR`은 `BSTR`을 공유하는 모든 `_bstr_t` 개체에 영향을 줍니다.  두 개 이상의 `_bstr_t`는 복사 생성자와 `operator=`를 사용하여 `BSTR`을 공유할 수 있습니다.  
  
## 예제  
 `GetBSTR`를 사용하는 예는 [\_bstr\_t::Assign](../cpp/bstr-t-assign.md)을 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)