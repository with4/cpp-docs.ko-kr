---
title: "컴파일러 오류 C3182 | Microsoft Docs"
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
  - "C3182"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3182"
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3182
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': WinRT 또는 관리되는 형식 내에서 using 선언 또는 액세스 선언 멤버를 사용할 수 없습니다.  
  
 [using](../../cpp/using-declaration.md) 선언은 모든 형식의 관리되는 클래스 내에서 유효하지 않습니다.  
  
 다음 샘플에서는 C3182 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  
  
 다음 샘플에서는 C3182 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3182b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc struct B {  
   void mf(int)  
   {  
   }  
};  
  
__gc struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char)  
   {  
   }  
};  
  
int main()  
{  
}  
```