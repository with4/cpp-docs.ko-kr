---
title: '방법: c + + Interop를 사용 하 여 ANSI 문자열 마샬링 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3690ca242b8c50c84c6eb4a8a7a437937268c6b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>방법: C++ Interop를 사용하여 ANSI 문자열 마샬링
이 항목에서는 ANSI 문자열 수 있는 방법을 보여 줍니다. c + + Interop 하지만.NET Framework를 사용 하 여 전달 <xref:System.String> ANSI로 변환에는 추가 단계는 유니코드 형식으로 문자열을 나타냅니다. 다른 문자열 형식 상호 작용을 하기 위한 다음 항목을 참조 합니다.  
  
-   [방법: C++ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [방법: C++ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 다음 코드 예제에서 사용 된 [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md) #pragma 지시문을 구현 하 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수가 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 때문에 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md), 성능 특성으로 유지할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 관리 되는 ANSI string을 사용 하 여 관리 되지 않는 함수에 전달 하는 방법을 보여 줍니다 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>합니다. 이 메서드는 관리 되지 않는 힙에서 메모리를 할당 하 고 변환을 수행 후 주소를 반환 합니다. 즉,는 고정 작업이 필요 하지 (하기 때문에 메모리 GC 힙에 관리 되지 않는 함수에 전달 되 고 되지 않은)에서 반환 되는 IntPtr 고 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 명시적으로 해제 해야 합니다. 그렇지 메모리 누수가 발생 합니다.  
  
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
  
## <a name="example"></a>예제  
 다음 예제는 ANSI 문자열은 관리 되지 않는 함수에 의해 호출 되는 관리 되는 함수에 액세스 하는 데 필요한 데이터 마샬링을입니다. 네이티브 문자열을 수신한 경우에 관리 되는 함수를 직접 사용 하거나 사용 하 여 관리 되는 문자열을 변환의 <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> 메서드를 표시 된 것 처럼 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)