---
title: "vector&lt;bool&gt;::reference::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operatorbool"
  - "vector<bool>::reference::operatorbool"
  - "bool"
  - "std::vector<bool>::reference::operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BOOL 연산자"
  - "reference::operator bool"
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# vector&lt;bool&gt;::reference::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`vector<bool>::reference`을 `bool`로 묵시적으로 변환합니다.  
  
## 구문  
  
```  
operator bool( ) const;  
```  
  
## 반환 값  
 [vector\<bool\>](../standard-library/vector-bool-class.md) 개체의 요소 부울 값.  
  
## 설명  
 `vector<bool>` 개체는 이 연산자로 수정할 수 없습니다.  
  
## 요구 사항  
 **헤더:** \<vector\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [vector\<bool\>::reference 클래스](../standard-library/vector-bool-reference-class.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)