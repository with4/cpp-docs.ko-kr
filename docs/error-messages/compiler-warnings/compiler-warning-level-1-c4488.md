---
title: 컴파일러 경고 (수준 1) C4488 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4488
dev_langs:
- C++
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a3c5fc64637d989066acfa90715c50504664231
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4488"></a>컴파일러 경고(수준 1) C4488
'function': 인터페이스 메서드 'interface_method'를 구현 하는 'keyword' 키워드를 필요 합니다.  
  
 클래스는 직접 상속 된 인터페이스의 모든 멤버를 구현 해야 합니다. 구현 된 멤버 public 액세스 가능성이 있어야 하 고 가상 표시 되어야 합니다.  
  
## <a name="example"></a>예제  
 구현 된 멤버가 public이 아니기 때문에 C4488 발생할 수 있습니다. 다음 샘플에서는 C4488 오류가 발생 합니다.  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## <a name="example"></a>예제  
 C4488 구현 된 멤버 가상 표시 되지 않은 경우에 발생할 수 있습니다. 다음 샘플에서는 C4488 오류가 발생 합니다.  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```