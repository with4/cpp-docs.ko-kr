---
title: "컴파일러 오류 C2360 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2360
dev_langs:
- C++
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 12b62d31c125dfc353623fa7cf10fce578698332
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2360"></a>컴파일러 오류 C2360
'i'의 초기화 'case' 레이블에 의해 생략 되었습니다.  
  
 초기화 `identifier` 건너 뛸 수 있습니다는 `switch` 문. 선언 블록 포함 하지 않는 한 이니셜라이저와 함께 선언 점프할 수 없습니다. (하지 않은 블록 내에 선언 된 변수는 범위 내에서 끝날 때까지 `switch` 문.)  
  
 다음 샘플에서는 C2360 오류가 생성 됩니다.  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```
