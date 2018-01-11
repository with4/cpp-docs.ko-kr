---
title: "Debug 클래스 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 236a40873d3cbd660f9999880d46df4f91632b2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="debug-class-ccli"></a>Debug 클래스(C++/CLI)
사용 하는 경우 <xref:System.Diagnostics.Debug> Visual c + + 응용 프로그램에서 동작 디버그 및 릴리스 빌드 간에 변경 되지 않습니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 동작 <xref:System.Diagnostics.Trace> 는 Debug 클래스에 대 한 동작과 동일 하지만 추적을 정의 하 고 기호에 따라 달라 집니다. 즉, 업그레이드 해야 합니다 `#ifdef` 릴리스 빌드에서 디버그 동작을 방지 하기 위해 모든 추적 관련 코드입니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 샘플에 출력 문을 사용 하 여 컴파일하면 여부에 관계 없이 항상 실행 **/DDEBUG** 또는 **/DTRACE**합니다.  
  
### <a name="code"></a>코드  
  
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
  
### <a name="output"></a>출력  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 예상 된 동작을 얻으려면 (즉, "test"가 출력 되지 인쇄 릴리스 빌드에 대 한)를 사용 해야 합니다는 `#ifdef` 및 `#endif` 지시문입니다. 이 해결 방법을 보여 주기 위해 아래 앞의 코드 예제는이 수정 됩니다.  
  
### <a name="code"></a>코드  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)