---
title: "컴파일러 경고 (수준 2) C4244 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 2) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'argument' : 'type1'에서 'type2'\(으\)로 변환하면서 데이터가 손실될 수 있습니다.  
  
 부동 소수점 형식을 정수 형식으로 변환했습니다.  데이터가 손실될 수 있습니다.  
  
 C4244가 발생하면 호환되는 형식을 사용하도록 프로그램을 변경하거나 가능한 값의 범위가 사용 중인 형식과 항상 호환되도록 코드에 몇 가지 논리를 추가해야 합니다.  
  
 C4244는 수준 3 및 4에서도 발생할 수 있습니다. 자세한 내용은 [컴파일러 경고 \(수준s 3 and 4\) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4244 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```