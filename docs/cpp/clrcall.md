---
title: "__clrcall | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__clrcall"
  - "__clrcall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__clrcall 키워드[C++]"
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __clrcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 관리 코드에서만 함수를 호출할 수 있도록 지정합니다.  관리 코드에서만 호출되는 모든 가상 함수에 `__clrcall`을 사용하십시오.  그러나 네이티브 코드에서 호출되는 함수에는 이 호출 규칙을 사용할 수 없습니다.  
  
 관리되는 함수에서 관리되는 가상 함수를 호출하거나 관리되는 함수에서 포인터를 통한 관리되는 함수를 호출할 때 `__clrcall`을 사용하여 성능을 개선하십시오.  
  
 진입점은 컴파일러에서 생성된 별도의 함수입니다.  함수에 네이티브 진입점과 관리되는 진입점이 둘 다 있을 경우 둘 중 하나는 함수 구현이 포함된 실제 함수입니다.  다른 함수는 실제 함수를 호출하고 공용 언어 런타임에서 PInvoke를 수행하게 하는 별도의 함수\(썽크\)입니다.  함수를 `__clrcall`로 표시할 경우 함수 구현이 MSIL이어야 하며 네이티브 진입점 함수가 생성되지 않음을 나타냅니다.  
  
 `__clrcall`이 지정되지 않은 경우 네이티브 함수의 주소를 가져올 때 컴파일러가 네이티브 진입점을 사용합니다.  `__clrcall`은 함수가 관리되며 관리에서 네이티브로 전환할 필요가 없음을 나타냅니다.  이 경우 컴파일러가 관리되는 진입점을 사용합니다.  
  
 **\/clr**\(**\/clr:pure** 또는 **\/clr:safe** 아님\)을 사용하고 `__clrcall`을 사용하지 않는 경우 함수의 주소를 가져오면 항상 네이티브 진입점 함수 주소가 반환됩니다.  `__clrcall`이 사용되면 네이티브 진입점 함수가 만들어지지 않으므로 진입점 썽크 함수가 아니라 관리되는 함수의 주소를 가져옵니다.  자세한 내용은 [이중 썽킹](../dotnet/double-thunking-cpp.md)을 참조하십시오.  
  
 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)는 모든 함수와 함수 포인터가 `__clrcall`이고 컴파일러는 compiland 안의 함수를 반드시 `__clrcall`로 표시해야 함을 의미합니다.  **\/clr:pure**가 사용되면 함수 포인터와 외부 선언에만 `__clrcall`을 지정할 수 있습니다.  
  
 함수에 MSIL 구현이 있으면 **\/clr**을 사용하여 컴파일된 기존의 C\+\+ 코드에서 직접 `__clrcall` 함수를 호출할 수 있습니다.  **\/clr**을 사용하여 함수가 컴파일된 경우에도 인라인 asm이 있고 CUP 관련 내장 함수를 호출하는 함수에서 직접 `__clrcall` 함수를 호출할 수 없습니다.  
  
 `__clrcall` 함수 포인터는 자신이 만들어진 응용 프로그램 도메인에서만 사용됩니다.  `__clrcall` 함수 포인터를 응용 프로그램 도메인에서 전달하는 대신 <xref:System.CrossAppDomainDelegate>를 사용하십시오.  자세한 내용은 [응용 프로그램 도메인 및 Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)을 참조하십시오.  
  
## 예제  
  
```  
// clrcall.cpp  
// compile with: /clr:oldSyntax /LD  
void __clrcall Test1( ) {}  
void (__clrcall *fpTest1)( ) = &Test1;  
```  
  
## 예제  
 `__clrcall`을 사용하여 함수가 선언되면 필요할 때\(예: 함수가 호출될 때\) 코드가 생성됩니다.  
  
```  
// clrcall2.cpp  
// compile with: /clr  
using namespace System;  
int __clrcall Func1() {  
   Console::WriteLine("in Func1");  
   return 0;  
}  
  
// Func1 hasn't been used at this point (code has not been generated),   
// so runtime returns the adddress of a stub to the function  
int (__clrcall *pf)() = &Func1;  
  
// code calls the function, code generated at difference address  
int i = pf();   // comment this line and comparison will pass  
  
int main() {  
   if (&Func1 == pf)  
      Console::WriteLine("&Func1 == pf, comparison succeeds");  
   else   
      Console::WriteLine("&Func1 != pf, comparison fails");  
  
   // even though comparison fails, stub and function call are correct  
   pf();  
   Func1();  
}  
```  
  
  **in Func1**  
**&Func1 \!\= pf, comparison fails**  
**in Func1**  
**in Func1**   
## 예제  
 다음 샘플에서는 함수 포인터를 정의하고 관리 코드에서만 함수 포인터를 호출할 수 있도록 선언합니다.  여기서는 컴파일러가 관리되는 함수를 직접 호출하고 네이티브 진입점\(이중 썽크 문제\)을 방지할 수 있습니다.  
  
```  
// clrcall3.cpp  
// compile with: /clr  
void Test() {  
   System::Console::WriteLine("in Test");  
}  
  
int main() {  
   void (*pTest)() = &Test;  
   (*pTest)();  
  
   void (__clrcall *pTest2)() = &Test;  
   (*pTest2)();  
}  
```  
  
## 참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)