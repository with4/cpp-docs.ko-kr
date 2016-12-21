---
title: "컴파일러 경고 (수준 1) C4486 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4486"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4486"
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4486
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : ref 클래스 또는 값 클래스의 전용 가상 메서드는 'sealed'로 표시되어야 합니다.  
  
 관리되는 클래스나 구조체의 전용 가상 멤버 함수는 액세스하거나 재정의할 수 없으므로 [sealed](../../windows/sealed-cpp-component-extensions.md)로 표시해야 합니다.  
  
## 예제  
 다음 샘플에서는 C4486 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4486.cpp  
// compile with: /clr /c /W1  
ref class B {  
private:  
   virtual void f() {}   // C4486  
   virtual void f1() sealed {}   // OK  
};  
```  
  
## 예제  
 다음 샘플에서는 sealed로 표시된 전용 가상 함수를 사용하는 방법을 보여 줍니다.  
  
```  
// C4486_b.cpp  
// compile with: /clr /c  
ref class B {};  
  
ref class D : B {};  
  
interface class I {  
   B^ mf();  
};  
  
ref class E : I {  
private:  
   virtual B^ g() sealed = I::mf {  
      return gcnew B;  
   }  
  
public:  
   virtual D^ mf() {  
      return gcnew D;  
   }  
};  
```