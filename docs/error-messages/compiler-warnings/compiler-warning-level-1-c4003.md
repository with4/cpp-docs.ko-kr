---
title: 컴파일러 경고 (수준 1) C4003 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a90202bfc06d50089e2ac283a5060bc431b9549c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4003"></a>컴파일러 경고 (수준 1) C4003
'identifier' 매크로의 실제 매개 변수가 부족합니다.  
  
 매크로 정의의 형식 매개 변수 개수가 매크로의 실제 매개 변수 개수를 초과 합니다. 누락 된 매개 변수가 빈 텍스트를 대체 하는 매크로 확장 합니다.  
  
 다음 샘플에서는 C4003 오류가 생성 됩니다.  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```