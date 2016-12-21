---
title: "방법: C++ Interop를 사용하여 유니코드 문자열 마샬링 | Microsoft Docs"
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
  - "C++ Interop, 문자열"
  - "데이터 마샬링[C++], 문자열"
  - "interop[C++], 문자열"
  - "마샬링[C++], 문자열"
  - "Unicode, 문자열 마샬링"
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++ Interop를 사용하여 유니코드 문자열 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목은 Visual C\+\+ 상호 운용성의 한 측면을 보여 줍니다.  자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
 다음 코드 예제에서는 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) \#pragma 지시문을 사용하여 동일한 파일에서 관리되는 함수와 관리되지 않는 함수를 구현합니다. 그러나 이러한 함수는 서로 다른 파일에 정의된 경우 동일한 방식으로 상호 운용됩니다.  관리되지 않는 함수만 포함된 파일은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 필요가 없습니다.  
  
 이 항목에서는 유니코드 문자열을 관리되는 함수에서 관리되지 않는 함수로 전달하거나 그 반대로 전달하는 방법을 보여 줍니다.  다른 문자열 형식과 상호 운용되는 데 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [방법: C\+\+ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## 예제  
 관리되는 함수에서 관리되지 않는 함수로 유니코드 문자열을 전달하려면 Vcclr.h에서 선언한 PtrToStringChars 함수를 사용하여 관리되는 문자열이 저장되어 있는 메모리에 액세스합니다.  이 주소는 네이티브 함수에 전달되므로 관리되지 않는 함수를 실행하는 동안 가비지 수집 사이클이 진행되는 경우 문자열 데이터가 재배치되지 않도록 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)를 사용하여 메모리를 고정해야 합니다.  
  
```  
// MarshalUnicode1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const wchar_t* p) {  
   printf_s("(native) received '%S'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("test string");  
   pin_ptr<const wchar_t> str = PtrToStringChars(s);  
  
   Console::WriteLine("(managed) passing string to native func...");  
   NativeTakesAString( str );  
}  
```  
  
## 예제  
 다음 예제에서는 관리되지 않는 함수가 호출한 관리되는 함수의 유니코드 문자열에 액세스하는 데 필요한 데이터 마샬링을 보여 줍니다.  관리되는 함수는 네이티브 유니코드 문자열을 받아 <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 메서드를 통해 관리되는 문자열로 변환합니다.  
  
```  
// MarshalUnicode2.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(wchar_t* s) {  
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);  
   Console::WriteLine("(managed) received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(unmanaged) calling managed func...\n";  
   ManagedStringFunc(L"test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)