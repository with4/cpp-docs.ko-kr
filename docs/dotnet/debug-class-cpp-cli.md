---
title: "Debug 클래스(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework[C++], Debug 클래스"
  - "Debug 클래스"
  - "Trace 클래스, Visual C++"
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Debug 클래스(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 응용 프로그램에서 <xref:System.Diagnostics.Debug>를 사용하는 경우 그 동작은 디버그 빌드와 릴리스 빌드 사이에 차이가 없습니다.  
  
## 설명  
 <xref:System.Diagnostics.Trace>의 동작은 Debug 클래스의 동작과 동일하지만 정의하려는 기호 TRACE에 종속됩니다.  즉, 릴리스 빌드에서 디버그 동작을 방지하려면 모든 Trace 관련 코드에 `#ifdef` 지시문을 사용해야 합니다.  
  
## 예제  
  
### 설명  
 다음 샘플에서는 컴파일할 때 **\/DDEBUG** 또는 **\/DTRACE**를 사용하는지 여부에 관계없이 항상 출력 문을 실행합니다.  
  
### 코드  
  
```  
// mcpp_debug_class.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
   Trace::Unindent();  
  
   Debug::WriteLine("test");  
}  
```  
  
### Output  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## 예제  
  
### 설명  
 원하는 동작을 얻으려면, 즉 릴리스 빌드에서 "test"가 출력되지 않게 하려면 `#ifdef` 및 `#endif` 지시문을 사용해야 합니다.  다음 예제는 앞의 코드 예제를 수정하여 이에 대해 설명합니다.  
  
### 코드  
  
```  
// mcpp_debug_class2.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
  
#ifdef TRACE   // checks for a debug build  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
#endif  
   Trace::Unindent();  
  
#ifdef DEBUG   // checks for a debug build  
   Debug::WriteLine("test");  
#endif   //ends the conditional block  
}  
```  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)