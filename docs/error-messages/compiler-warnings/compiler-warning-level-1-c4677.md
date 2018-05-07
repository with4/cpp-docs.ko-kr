---
title: 컴파일러 경고 (수준 1) C4677 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3511ad3100bf695cec5df97703b39e5926c71c11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4677"></a>컴파일러 경고(수준 1) C4677
'function': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 형식 'private_type'  
  
 어셈블리 외부에 개인 액세스 권한이 있는 형식을 사용 하는 어셈블리 외부에서 public 액세스 가능성을 가지는 형식입니다. 공용 어셈블리 유형을 참조 하는 구성 요소 어셈블리 전용 형식 참조 하는 멤버 또는 형식 멤버를 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4677 오류가 발생 합니다.  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```