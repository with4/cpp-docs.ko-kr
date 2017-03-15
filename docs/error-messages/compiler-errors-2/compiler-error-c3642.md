---
title: "컴파일러 오류 C3642 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3642"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3642"
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C3642
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'return\_type\/args' : \_\_clrcall 호출 규칙이 있는 함수를 네이티브 코드에서 호출할 수 없습니다.  
  
 [\_\_clrcall](../../cpp/clrcall.md) 호출 규칙을 사용하여 표시한 함수는 네이티브\(비관리\) 코드에서 호출할 수 없습니다.  
  
 *return\_type\/args*는 호출하려는 `__clrcall` 함수의 형식이거나 함수의 이름입니다.  함수 포인터를 통해 호출할 때 형식이 사용됩니다.  
  
 네이티브 컨텍스트에서 관리되는 함수를 호출하려면 `__clrcall` 함수를 호출하는 "래퍼" 함수를 추가합니다.  또는 CLR 마샬링 메커니즘을 사용할 수 있습니다. 자세한 내용은 [방법: PInvoke를 사용하여 함수 포인터 마샬링](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)을 참조하십시오.  
  
 다음 샘플에서는 C3642 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```