---
title: 컴파일러 오류 C2274 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2274
dev_langs:
- C++
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfd9bda3f3b0ab267ec008443dd865334e1b765e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2274"></a>컴파일러 오류 C2274
'type':의 오른쪽에 '.' 연산자  
  
 형식 멤버 액세스 (.) 연산자의 오른쪽 피연산자도 나타납니다.  
  
 이 오류는 사용자 정의 형식 변환에 액세스 하려는 경우에 발생할 수 있습니다. 키워드를 사용 하 여 `operator` 간의 기간 및 `type`합니다.  
  
 다음 샘플에서는 C2286을 생성합니다.  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```