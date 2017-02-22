---
title: "컴파일러 오류 C3533 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3533"
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'형식': 매개 변수는 'auto'가 포함된 형식을 가질 수 없습니다.  
  
 기본 [\/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션이 적용 중일 경우에는 메서드 또는 템플릿 매개 변수를 `auto` 키워드와 함께 선언할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  매개 변수 선언에서 `auto` 키워드를 제거합니다.  
  
## 예제  
 다음 예제에서는 `auto` 키워드가 있는 함수 매개 변수가 선언되고 **\/Zc:auto**를 사용하여 컴파일되기 때문에 C3535가 발생합니다.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## 예제  
 다음 예제에서는 `auto` 키워드가 있는 템플릿 매개 변수가 선언되고 **\/Zc:auto**를 사용하여 컴파일되기 때문에 C3535가 발생합니다.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [\/Zc:auto\(변수 형식 추론\)](../../build/reference/zc-auto-deduce-variable-type.md)