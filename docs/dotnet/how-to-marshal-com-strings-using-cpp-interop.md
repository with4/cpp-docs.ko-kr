---
title: "방법: C++ Interop를 사용하여 COM 문자열 마샬링 | Microsoft Docs"
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
  - "COM[C++], 문자열 마샬링"
  - "데이터 마샬링[C++], 문자열"
  - "interop[C++], 문자열"
  - "마샬링[C++], 문자열"
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++ Interop를 사용하여 COM 문자열 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 관리되는 함수에서 관리되지 않는 함수로, 또는 그 반대로 BSTR\(COM 프로그래밍에서 자주 사용하는 기본 문자열 형식\)가 전달되는 방식에 대해 설명합니다.  다른 문자열 형식과 상호 운용되는 데 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [방법: C\+\+ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 다음 코드 예제에서는 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) \#pragma 지시문을 사용하여 동일한 파일에서 관리되는 함수와 관리되지 않는 함수를 구현합니다. 그러나 이러한 함수는 서로 다른 파일에 정의된 경우 동일한 방식으로 상호 운용됩니다.  관리되지 않는 함수만 포함된 파일은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 필요가 없습니다.  
  
## 예제  
 다음 예제에서는 관리되는 함수에서 관리되지 않는 함수로 BSTR\(COM 프로그래밍에서 사용하는 문자열 형식\)가 전달될 수 있는 방식에 대해 설명합니다.  호출하는 관리되는 함수에서는 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A>을 사용하여 .NET System.String의 내용을 BSTR로 표현한 개체의 주소를 얻습니다.  이 포인터는 관리되지 않는 함수가 실행될 때 가비지 수집 주기 동안 실제 주소가 변경되지 않도록 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)을 사용하여 고정됩니다.  가비지 수집기는 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)가 범위를 벗어날 때까지 메모리를 이동하지 않습니다.  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## 예제  
 다음 예제에서는 관리되지 않는 함수에서 관리되는 함수로 BSTR가 전달되는 방식에 대해 설명합니다.  BSTR를 전달받는 관리되는 함수에서는 BSTR 문자열을 그대로 사용하거나 기타 관리되는 함수와 함께 사용하기 위해 <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A>를 사용하여 <xref:System.String>으로 변환할 수 있습니다.  BSTR를 나타내는 메모리는 가비지 수집이 없는 관리되지 않는 힙에 할당되므로 고정이 필요하지 않습니다.  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)