---
title: "컴파일러 오류 C3352 | Microsoft Docs"
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
  - "C3352"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3352"
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3352
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 지정한 함수가 'type' 대리자 형식과 일치하지 않습니다.  
  
 `function`의 매개 변수 목록과 대리자가 일치하지 않습니다.  
  
 자세한 내용은 [delegate](../../windows/delegate-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3352 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3352.cpp  
// compile with: /clr  
delegate int D( int, int );  
ref class C {  
public:  
   int mf( int ) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352  
}  
```  
  
 다음 샘플에서는 C3352 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3352_2.cpp  
// compile with: /clr:oldSyntax  
__delegate int D(int, int);  
  
__gc class C {  
public:  
   int mf(int) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C *pC = new C;  
   System::Delegate *pD = new D(pC, &C::mf);   // C3352  
}  
```