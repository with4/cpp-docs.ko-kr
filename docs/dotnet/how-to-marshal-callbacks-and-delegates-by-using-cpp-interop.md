---
title: "방법: c + + Interop를 사용 하 여 마샬링 콜백 및 대리자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2a835dbdbce23f7f92f13fabd038d6e294345981
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>방법: C++ Interop를 사용하여 콜백 및 대리자 마샬링
이 항목 마샬링하는 방법을 보여 줍니다 하 고 Visual c + +를 사용 하 여 관리 코드와 비관리 코드 (콜백의 관리 되는 버전)을 위임 합니다.  
  
 다음 코드 예제에서 사용 된 [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md) #pragma 지시문을 구현 하 관리는 관리 되지 않는 동일한 파일의 함수는 함수를 별도 파일에 정의 될 수도 있습니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다는 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 관리 되는 대리자를 트리거하는 관리 되지 않는 API를 구성 하는 방법을 보여 줍니다. 관리 되는 대리자가 interop 메서드 중 하나를 <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, 대리자에 대 한 기본 진입점을 검색 하는 데 사용 됩니다. 그러면이 주소는 관리 되는 함수로 구현 된 사실 모르는 상태로 호출 하는 관리 되지 않는 함수에 전달 됩니다.  
  
 다음에 유의 있지만 핀에 필요 하지 않은 사용 하 여 대리자 [pin_ptr (C + + /cli CLI)](../windows/pin-ptr-cpp-cli.md) 재배치 하거나 가비지 수집기에 의해 삭제 하지 못하게 합니다. 예기치 않은 가비지 수집에 보호 필요 하지만 고정 컬렉션이 않도록 또한 재배치 방지 있지만 필요한 것 보다 더 나은 보호를 제공 합니다.  
  
 대리자에는 가비지 수집에 의해 다시 있는 경우, 그 영향을 주지 것입니다 해도 내부에 있는 관리 되는 콜백 하므로 <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> 대리자의 재배치 하지만 삭제를 방지 하는 대리자에 대 한 참조를 추가 하는 데 사용 됩니다. Pin_ptr 대신 GCHandle을 사용 하 여 관리 되는 힙의 조각화 가능성이 줄어듭니다.  
  
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
  
## <a name="example"></a>예제  
 다음 예제에서는 앞의 예와 유사 하지만 경우 제공 된 함수 포인터 저장 되어 관리 되지 않는 API에서 있으므로 호출할 수 있습니다 언제 든 지 가비지 수집 임의의 기간에 대 한 보류 수를 요구 합니다. 다음 예제에서는의 전역 인스턴스를 사용 하 여 결과적으로, <xref:System.Runtime.InteropServices.GCHandle> 대리자 재배치 되는, 독립적인 함수 범위의 되 고 하지 못하도록 합니다. 첫 번째 예제에서 설명 했 듯이 pin_ptr를 사용 하 여 이러한 예제에 대 한 필요는 없지만 경우으로 작동 하지 누르고, pin_ptr의 범위를 하나의 함수로 제한 됩니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)