---
title: "컴파일러 오류 C2050 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2050
dev_langs:
- C++
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ab67a523b7cc65f29ab443fc189d0614026fc2cd
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2050"></a>컴파일러 오류 C2050
switch 식이 정수 계열이 아닙니다.  
  
 `switch` 식을 정수가 아닌 값으로 계산 합니다. 이 오류를 해결 하려면 switch 문에서 정수 계열 값만 사용 합니다.  
  
 다음 샘플에서는 C2050 오류가 생성 됩니다.  
  
```  
// C2050.cpp  
int main() {  
   int a = 1;  
   switch ("a") {   // C2050  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C2050b.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```
