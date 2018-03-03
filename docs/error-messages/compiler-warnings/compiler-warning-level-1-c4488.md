---
title: "컴파일러 경고 (수준 1) C4488 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4488
dev_langs:
- C++
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad82e9dc85d818aacd78aaeb287777bd91927a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4488"></a>컴파일러 경고(수준 1) C4488
'function': 인터페이스 메서드 'interface_method'를 구현 하는 'keyword' 키워드를 필요 합니다.  
  
 클래스는 직접 상속 된 인터페이스의 모든 멤버를 구현 해야 합니다. 구현 된 멤버 public 액세스 가능성이 있어야 하 고 가상 표시 되어야 합니다.  
  
## <a name="example"></a>예  
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
  
## <a name="example"></a>예  
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