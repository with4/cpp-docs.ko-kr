---
title: "방법: C++ Interop를 사용하여 ANSI 문자열 마샬링 | Microsoft Docs"
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
  - "ANSI[C++], 문자열 마샬링"
  - "C++ Interop, 문자열"
  - "데이터 마샬링[C++], 문자열"
  - "interop[C++], 문자열"
  - "마샬링[C++], 문자열"
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++ Interop를 사용하여 ANSI 문자열 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 C\+\+ Interop를 사용하여 ANSI 문자열을 전달하는 방법을 보여 줍니다. .NET Framework <xref:System.String>은 유니코드 형식의 문자열을 나타내므로 문자열을 ANSI로 변환하는 추가 단계가 필요합니다.  다른 문자열 형식과 상호 운용하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [방법: C\+\+ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 다음 코드 예제에서는 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) \#pragma 지시문을 사용하여 동일한 파일에서 관리되는 함수와 관리되지 않는 함수를 구현합니다. 그러나 이러한 함수는 서로 다른 파일에 정의된 경우 동일한 방식으로 상호 운용됩니다.  관리되지 않는 함수만 포함된 파일은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 필요가 없으므로 성능을 그대로 유지할 수 있습니다.  
  
## 예제  
 이 예제에서는 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>를 사용하여 관리되는 함수에서 관리되지 않는 함수로 ANSI 문자열을 전달하는 방법을 보여 줍니다.  이 메서드는 관리되지 않는 힙에 메모리를 할당하고 변환을 수행한 다음 주소를 반환합니다.  즉, GC 힙의 메모리가 관리되지 않는 함수에 전달되지 않으므로 고정 작업이 필요하지 않으며, <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>에서 반환되는 IntPtr를 명시적으로 해제하지 않으면 메모리 누수가 발생합니다.  
  
```  
// MarshalANSI1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const char* p) {  
   printf_s("(native) received '%s'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("sample string");  
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);  
   const char* str = static_cast<const char*>(ip.ToPointer());  
  
   Console::WriteLine("(managed) passing string...");  
   NativeTakesAString( str );  
  
   Marshal::FreeHGlobal( ip );  
}  
```  
  
## 예제  
 다음 예제에서는 관리되지 않는 함수가 호출한 관리되는 함수의 ANSI 문자열에 액세스하는 데 필요한 데이터 마샬링을 보여 줍니다.  관리되는 함수는 네이티브 문자열을 받을 때 이를 직접 사용하거나 다음과 같이 <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> 메서드를 사용하여 이 문자열을 관리되는 문자열로 변환할 수 있습니다.  
  
```  
// MarshalANSI2.cpp  
// compile with: /clr  
#include <iostream>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(char* s) {  
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));  
   Console::WriteLine("(managed): received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(native) calling managed func...\n";  
   ManagedStringFunc("test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)