---
title: 컴파일러 오류 C2051 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2051
dev_langs:
- C++
helpviewer_keywords:
- C2051
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49817ff2ad99a2cd3f23d1d0cda1456dc2c30b9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165089"
---
# <a name="compiler-error-c2051"></a>컴파일러 오류 C2051
case 식이 상수가 아닙니다.  
  
 Case 식은 정수 상수 여야 합니다.  
  
 다음 샘플에서는 C2051 오류가 생성 됩니다.  
  
```  
// C2051.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case x:   // C2051 use constant expression to resolve error  
         break;  
      default:  
         break;  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C2051b.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```