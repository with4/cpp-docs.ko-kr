---
title: "_bstr_t::GetAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::GetAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddress 메서드"
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::GetAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 기존 문자열을 해제하고 새로 할당된 문자열의 주소를 반환합니다.  
  
## 구문  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## 반환 값  
 `_bstr_t`로 래핑되는 `BSTR`에 대한 포인터입니다.  
  
## 설명  
 `GetAddress`는 `BSTR`을 공유하는 모든 `_bstr_t` 개체에 영향을 줍니다.  두 개 이상의 `_bstr_t`는 복사 생성자와 `operator=`를 사용하여 `BSTR`을 공유할 수 있습니다.  
  
## 예제  
 `GetAddress`의 사용 예시는 [\_bstr\_t::Assign](../cpp/bstr-t-assign.md)을 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)