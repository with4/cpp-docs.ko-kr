---
title: "vector&lt;bool&gt;::reference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference"
  - "std::vector<bool>::reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector<bool> 참조 클래스"
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# vector&lt;bool&gt;::reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`vector<bool>::reference` 클래스는 [vector\<bool\> 클래스](../standard-library/vector-bool-class.md)에서 `bool&`을 시뮬레이션하도록 제공된 프록시입니다.  
  
## 설명  
 C\+\+는 기본적으로 비트에 직접 참조를 허용하지 않으므로 시뮬레이션된 참조가 필요하지 않습니다.  `vector<bool>`는 요소당 1비트만 사용하며, 이 프록시 클래스만 사용하여 참조할 수 있습니다.  하지만, 특정 할당은 유효하지 않으므로 참조 시뮬레이션이 완전하지 않습니다.  예를 들어, `vector<bool>::reference` 개체의 주소를 확인할 수 없으므로 [vector\<bool\>::operator&#91;&#93;](../Topic/vector%3Cbool%3E::operator.md) 코드는 올바르지 않습니다.  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error - do not use  
    bool& refb = vb[1];   // conversion error - do not use  
  
```  
  
### 멤버 함수  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|벡터 요소의 부울 값을 반전합니다.|  
|[연산자 bool](../standard-library/vector-bool-reference-operator-bool.md)|`vector<bool>::reference`을 `bool`로 묵시적으로 변환합니다.|  
|[operator\=](../standard-library/vector-bool-reference-operator-assign.md)|비트에 부울 값을 할당하거나 참조된 요소에 저장된 값을 비트에 할당합니다.|  
  
## 요구 사항  
 **헤더**: \<vector\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<vector\>](../standard-library/vector.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)