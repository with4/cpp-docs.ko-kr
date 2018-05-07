---
title: 컴파일러 경고 (수준 4) C4204 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4204
dev_langs:
- C++
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a803c81ea0f2fd6ce4b5a8f26eb626e89a32a9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4204"></a>컴파일러 경고(수준 4) C4204
비표준 확장이 사용 됨: 비상수 집합체 이니셜라이저입니다.  
  
 Microsoft 확장 (/Ze) 상수가 아닌 값으로 집계 형식 (배열, 구조체, 공용 구조체 및 클래스)을 초기화할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 이러한 초기화는 ANSI 규격 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).