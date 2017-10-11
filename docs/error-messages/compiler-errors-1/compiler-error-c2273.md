---
title: "컴파일러 오류 C2273 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2273
dev_langs:
- C++
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 58f7f13303b9941cf07e90685d68d7114213ea2d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2273"></a>컴파일러 오류 C2273
'type': '->' 연산자의 오른쪽에 사용할 수 없습니다.  
  
 오른쪽 피연산자와 형식이 표시는 `->` 연산자입니다.  
  
 이 오류는 사용자 정의 형식 변환에 액세스 하려는 경우에 발생할 수 있습니다. ->와 `operator` 사이에 `type` 키워드를 사용하십시오.  
  
 다음 샘플에서는 C2273 오류가 생성 됩니다.  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```
