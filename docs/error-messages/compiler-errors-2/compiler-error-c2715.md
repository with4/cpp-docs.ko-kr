---
title: "컴파일러 오류 C2715 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2715"
ms.assetid: c81567a7-5b65-468f-aaf9-835f91e468e4
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 컴파일러 오류 C2715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 이 형식을 Throw\/Catch할 수 없습니다.  
  
 관리 코드에서 예외 처리를 사용하는 경우 값 형식은 유효한 인수가 아닙니다. 자세한 내용은 [Exception Handling](../../windows/exception-handling-cpp-component-extensions.md)를 참조하십시오.  
  
```  
// C2715a.cpp  
// compile with: /clr  
using namespace System;  
  
value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw ((V^)v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(V^ pv) { if ( pv->i == 10 ) {  
         Console::WriteLine("caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine("catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine("catch looks REALLY bad");  
   }  
}  
```  
  
 Managed Extensions for C\+\+에서 예외 처리를 사용할 경우 [\_\_value](../../misc/value.md) 형식 또는 [\_\_gc](../../misc/gc.md) 포인터는 유효한 인수가 아닙니다.  이 오류를 해결하려면 [\_\_box](../../misc/box.md) 키워드를 사용하여 인수를 묶으십시오.  
  
 다음 샘플에서는 C2715 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2715b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
  
__value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw __box(v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(__box V *pv) { if ( pv->i == 10 ) {  
         Console::WriteLine(S"caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine(S"catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine(S"catch looks REALLY bad");  
   }  
}  
```