---
title: "컴파일러 오류 C2273 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2273
dev_langs: C++
helpviewer_keywords: C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c08e746034d066dd73d172045ce796bf4f74de0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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