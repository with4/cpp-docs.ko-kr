---
title: 컴파일러 오류 C2191 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa4b590b494355450909032c78822553004beddc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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