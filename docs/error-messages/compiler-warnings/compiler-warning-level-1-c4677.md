---
title: "컴파일러 경고 (수준 1) C4677 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7af724ad56c3a84ffb8ef48e13d14bee97db14df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4677"></a>컴파일러 경고(수준 1) C4677
'function': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 형식 'private_type'  
  
 어셈블리 외부에 개인 액세스 권한이 있는 형식을 사용 하는 어셈블리 외부에서 public 액세스 가능성을 가지는 형식입니다. 공용 어셈블리 유형을 참조 하는 구성 요소 어셈블리 전용 형식 참조 하는 멤버 또는 형식 멤버를 사용할 수 없습니다.  
  
## <a name="example"></a>예  
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