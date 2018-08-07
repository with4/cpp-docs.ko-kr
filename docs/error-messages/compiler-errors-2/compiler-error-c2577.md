---
title: 컴파일러 오류 C2577 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2577
dev_langs:
- C++
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af4fb6d5a2d7621df1b11e9040ca7dd4f5551289
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232053"
---
# <a name="compiler-error-c2577"></a>컴파일러 오류 C2577
'member': 소멸자/종료자는 반환 형식을 가질 수 없습니다  
  
 소멸자 또는 종료자의 값을 반환할 수 `void` 또는 기타 형식입니다. 제거는 `return` 소멸자 정의에서 문입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2577 오류가 발생 합니다.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```