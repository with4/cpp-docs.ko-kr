---
title: "방법: c + + Interop를 사용 하 여 COM 문자열 마샬링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 45a79f3aa78d229c71aba5a1d1144d05afe7bbd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>방법: C++ Interop를 사용하여 COM 문자열 마샬링
이 항목에서 설명 하는 BSTR (COM 프로그래밍에서 선호 하는 기본 문자열 형식) 수 있는 방법은 관리 되지 않는 함수를 코드와 관리 되는 전달 합니다. 다른 문자열 형식 상호 작용을 하기 위한 다음 항목을 참조 합니다.  
  
-   [방법: C++ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [방법: C++ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 다음 코드 예제에서 사용 된 [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md) #pragma 지시문을 구현 하 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수가 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 BSTR (COM 프로그래밍에서 사용 하는 문자열 형식)를 전달할 수 있습니다 어떻게 관리 되는 관리 되지 않는 함수입니다. 호출 함수 사용 하 여 관리 되는 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> .NET System.String의 내용에 대 한 BSTR 표현의 주소를 가져옵니다. 이 포인터를 사용 하 여 고정 [pin_ptr (C + + /cli CLI)](../windows/pin-ptr-cpp-cli.md) 관리 되지 않는 함수를 실행 하는 동안 실제 주소가 가비지 수집 주기 동안 변경 되지 않도록 할 수 있도록 합니다. 가비지 수집기가 이동 될 때까지 메모리에서 허용 되지 않습니다는 [pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md) 범위를 벗어나게 합니다.  
  
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
  
## <a name="example"></a>예  
 다음 예제에서는 BSTR 전달 하는 방법 관리 되지 않는 함수에 관리 되지 않는 합니다. 관리 되는 함수에 문자열을 사용 하 여 BSTR로 하거나 사용 하 여 수신 <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> 변환할는 <xref:System.String> 다른 용도로 함수를 관리 합니다. BSTR를 나타내는 메모리 할당 되기 때문에 관리 되지 않는 힙에서 고정 작업이, 필요 하지는 관리 되지 않는 힙에서 가비지 컬렉션 때문에 있습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)