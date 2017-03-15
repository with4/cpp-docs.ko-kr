---
title: "방법: C++ Interop를 사용하여 콜백 및 대리자 마샬링 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Interop, 콜백 및 대리자"
  - "콜백[C++], 마샬링"
  - "데이터 마샬링[C++], 콜백 및 대리자"
  - "대리자[C++], 마샬링"
  - "interop[C++], 콜백 및 대리자"
  - "마샬링[C++], 콜백 및 대리자"
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++ Interop를 사용하여 콜백 및 대리자 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 Visual C\+\+를 사용하여 관리 코드와 비관리 코드 사이에서 콜백 및 대리자\(콜백의 관리되는 버전\)를 마샬링하는 방법을 보여 줍니다.  
  
 다음 코드 예제에서는 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) \#pragma 지시문을 사용하여 동일한 파일에서 관리되는 함수와 관리되지 않는 함수를 구현합니다. 그러나 이러한 함수를 서로 다른 파일에 정의할 수도 있습니다.  관리되지 않는 함수만 포함된 파일은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 필요가 없습니다.  
  
## 예제  
 다음 예제에서는 관리되지 않는 API를 구성하여 관리되는 대리자를 트리거하는 방법을 보여 줍니다.  관리되는 대리자를 만들고 interop 메서드의 하나인 <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>를 사용하여 대리자의 내부 진입점을 검색합니다.  그런 다음 이 주소를 관리되지 않는 함수로 전달하고 이 함수에서는 관리되는 함수로 구현되었다는 것을 전혀 모르는 상태로 이 주소를 호출합니다.  
  
 가비지 수집기가 대리자를 재배치하거나 삭제하지 않도록 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)를 사용하여 대리자를 고정할 수도 있지만 이는 필요하지 않습니다.  성급한 가비지 수집은 막아야 하지만, 대리자를 고정하면 가비지 수집뿐만 아니라 재배치까지 방지되기 때문에 필요한 수준 이상의 보호가 제공됩니다.  
  
 가비지 수집기가 대리자를 재배치해도 내부에 있는 관리되는 콜백은 영향을 받지 않습니다. 따라서 대리자의 삭제를 방지하지만 재배치는 허용하는 <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A>를 사용하여 대리자에 대한 참조를 추가합니다.  pin\_ptr 대신 GCHandle을 사용하면 관리되는 힙이 단편화될 가능성이 줄어듭니다.  
  
```  
// MarshalDelegate1.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n, m);  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   return n + m;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   GCHandle gch = GCHandle::Alloc(fp);  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
// force garbage collection cycle to prove  
// that the delegate doesn't get disposed  
   GC::Collect();  
  
   int answer = TakesCallback(cb, 243, 257);  
  
// release reference to delegate  
   gch.Free();  
}  
```  
  
## 예제  
 다음 예제는 이전 예제와 비슷하지만, 제공되는 함수 포인터가 관리되지 않는 API에 의해 저장되어 언제든지 호출될 수 있으므로 임의의 시간 동안 가비지 수집을 막아야 한다는 점이 다릅니다.  따라서 다음 예제에서는 <xref:System.Runtime.InteropServices.GCHandle>의 전역 인스턴스를 사용하여 함수 범위에 관계없이 대리자가 재배치되지 않도록 합니다.  첫 번째 예제에서 설명한 것과 같이 이들 예제에서는 pin\_ptr가 필요하지 않으며, 특히 이 경우에는 pin\_ptr의 범위가 단일 함수로 제한되므로 아예 작동하지 않습니다.  
  
```  
// MarshalDelegate2.cpp  
// compile with: /clr   
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
static ANSWERCB cb;  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   cb = fp;  
   if (cb) {  
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);  
      return cb(n, m);  
   }  
   printf_s("[unmanaged] unregistering callback");  
   return 0;  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
  
   return n + m + x;  
}  
  
static GCHandle gch;  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
  
   gch = GCHandle::Alloc(fp);  
  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TakesCallback(cb, 243, 257);  
  
   // possibly much later (in another function)...  
  
   Console::WriteLine("[managed] releasing callback mechanisms...");  
   TakesCallback(0, 243, 257);  
   gch.Free();  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)