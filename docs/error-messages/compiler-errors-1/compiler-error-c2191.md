---
title: "컴파일러 오류 C2191 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8c8f1848fedf7bf811a335043693980855293694
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2191"></a>컴파일러 오류 C2191
두 번째 매개 변수 목록이 첫째 보다 깁니다.  
  
 C 함수를 한 번 더 긴 매개 변수 목록 사용 하 여 선언 되었습니다. C에서 오버 로드 된 함수를 지원 하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2191 오류가 생성 됩니다.  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```
