---
title: "컴파일러 오류 C3532 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3532"
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'형식': 'auto'를 잘못 사용했습니다.  
  
 지정된 형식은 `auto` 키워드를 사용하여 선언할 수 없습니다.  예를 들어, `auto` 키워드를 사용하여 배열 또는 메서드 반환 형식을 선언할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  초기화 식이 올바른 형식을 반환하는지 확인합니다.  
  
2.  배열 또는 메서드 반환 형식을 선언하지 않았는지 확인합니다.  
  
## 예제  
 다음 예제에서는 `auto` 키워드를 사용하여 메서드 반환 형식을 선언할 수 없으므로 C3532가 발생합니다.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## 예제  
 다음 예제에서는 `auto` 키워드를 사용하여 배열을 선언할 수 없으므로 C3532가 발생합니다.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)