---
title: 컴파일러 오류 C3280 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3280
dev_langs:
- C++
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b47d9f552b84db462734d3ae7dd83fd1257d2044
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3280"></a>컴파일러 오류 C3280
'class': 관리되는 형식의 멤버-함수는 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 관리되는 클래스 멤버 함수를 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 다음 샘플에서는 C3280을 생성합니다.  
  
```  
// C3280_2.cpp  
// compile with: /clr  
ref struct A {  
   void func();  
};  
  
#pragma managed(push,off)  
  
void A::func()   // C3280  
{  
}  
  
#pragma managed(pop)  
```  
