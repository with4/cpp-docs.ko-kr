---
title: "관리 코드에서 네이티브 함수 호출 | Microsoft Docs"
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
  - "관리 코드에서 네이티브 함수 호출"
  - "interop[C++], 관리 코드에서 네이티브 함수 호출"
  - "상호 운용성[C++], 관리 코드에서 네이티브 함수 호출"
  - "관리 코드[C++], 상호 운용성"
  - "관리 코드에서 호출된 네이티브 함수[C++]"
  - "플랫폼 호출[C++], 상호 운용성"
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 관리 코드에서 네이티브 함수 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

공용 언어 런타임은 네이티브 DLL\(동적 연결 라이브러리\)에서 관리 코드가 C 스타일 함수를 호출할 수 있도록 하는 플랫폼 호출 서비스인 PInvoke를 제공합니다.  런타임의 COM 상호 운용성과 IJW\(It Just Works\) 메커니즘에 동일한 데이터 마샬링이 사용됩니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [A Closer Look at Platform Invoke](http://msdn.microsoft.com/ko-kr/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 이 단원의 샘플은 `PInvoke`를 사용하는 방법에 대해서만 설명합니다.  `PInvoke`를 사용하면 프로시저 마샬링 코드를 작성하는 대신 마샬링 정보를 특성에 선언적으로 제공할 수 있으므로 사용자 지정된 데이터 마샬링을 간소화할 수 있습니다.  
  
> [!NOTE]
>  마샬링 라이브러리는 네이티브 및 관리 환경 사이에 최적화된 방법으로 데이터를 마샬링하는 대안을 제공합니다.  마샬링 라이브러리에 대한 자세한 내용은 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)를 참조하십시오.  마샬링 라이브러리는 데이터에만 사용할 수 있고 함수에는 사용할 수 없습니다.  
  
## PInvoke 및 DllImport 특성  
 다음 예제는 Visual C\+\+ 프로그램에서 `PInvoke`를 사용하는 방법을 보여 줍니다.  네이티브 함수 puts는 msvcrt.dll에서 정의됩니다.  DllImport 특성은 puts를 선언하는 데 사용됩니다.  
  
```  
// platform_invocation_services.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", CharSet=CharSet::Ansi)]  
extern "C" int puts(String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 다음 샘플은 위 샘플과 동일한 기능을 수행하지만 IJW를 사용합니다.  
  
```  
// platform_invocation_services_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <stdio.h>  
  
int main() {  
   String ^ pStr = "Hello World!";  
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();   
   puts(pChars);  
  
   Marshal::FreeHGlobal((IntPtr)pChars);  
}  
```  
  
### IJW의 이점  
  
-   프로그램에 사용되는 관리되지 않는 API에 대해 `DLLImport` 특성 선언을 작성할 필요가 없습니다.  헤더 파일을 포함하고 가져오기 라이브러리를 링크하기만 하면 됩니다.  
  
-   IJW 메커니즘은 속도가 약간 더 빠릅니다. 예를 들어 IJW 스텁에서는 데이터 항목을 고정하거나 복사해야 하는지 검사할 필요가 없습니다. 이 동작은 개발자가 명시적으로 수행하기 때문입니다.  
  
-   성능 문제를 쉽게 파악할 수 있습니다.  이 경우 유니코드 문자열을 ANSI 문자열로 변환하려고 한다는 점과 메모리 할당 및 할당 취소가 관련되어 있다는 점이 성능과 관련되어 있습니다.  IJW를 사용하여 코드를 작성하는 개발자는 `_putws`를 호출하고 `PtrToStringChars`를 사용하면 성능이 향상된다는 사실을 파악할 수 있습니다.  
  
-   동일한 데이터를 사용하여 관리되지 않는 API를 여러 개 호출하는 경우 이를 한 번만 마샬링하고 마샬링된 복사본을 전달하면 매번 다시 마샬링하는 것보다 훨씬 더 효율적으로 작업할 수 있습니다.  
  
### IJW의 단점  
  
-   마샬링은 종종 해당하는 기본값이 있는 특성에 의해 지정되는 대신 아니라 코드에서 명시적으로 지정되어야 합니다.  
  
-   마샬링 코드는 인라인이므로 응용 프로그램 논리의 흐름이 침해될 소지가 많습니다.  
  
-   명시적 마샬링 API는 32비트에서 64비트로의 이식성에 대해 `IntPtr` 형식을 반환하므로 `ToPointer` 호출을 추가로 사용해야 합니다.  
  
 C\+\+에서 노출되는 특정 메서드는 더 효율적이고 명시적인 메서드인 반면 코드가 더 복잡해진다는 단점이 있습니다.  
  
 응용 프로그램에서 관리되지 않는 데이터 형식을 주로 사용하거나 .NET Framework API보다 관리되지 않는 API를 더 많이 호출하는 경우 IJW 기능을 사용하는 것이 좋습니다.  대부분의 관리되는 응용 프로그램에서 관리되지 않는 API를 가끔씩 호출하는 경우 어느 쪽을 선택할지는 일률적으로 판단할 수 있는 문제가 아닙니다.  
  
## Windows API와 함께 PInvoke 사용  
 PInvoke는 Windows에서 함수를 호출하는 데 편리하게 사용할 수 있습니다.  
  
 이 예제에서 Visual C\+\+ 프로그램은 Win32 API의 일부인 MessageBox 함수와 상호 작용합니다.  
  
```  
// platform_invocation_services_4.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Ansi)]  
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);  
  
int main() {  
   String ^ pText = "Hello World! ";  
   String ^ pCaption = "PInvoke Test";  
   MessageBox(0, pText, pCaption, 0);  
}  
```  
  
 Hello World\!라는 텍스트가 들어 있고 제목이 PInvoke Test인 메시지 상자가 출력됩니다.  
  
 마샬링 정보는 PInvoke에서 DLL의 함수를 조회하는 데도 사용됩니다.  user32.dll에는 실제로 MessageBox 함수가 없지만 CharSet\=CharSet::Ansi를 사용하면 PInvoke에서 유니코드 버전인 MessageBoxW 대신 ANSI 버전인 MessageBoxA를 사용할 수 있습니다.  일반적으로는 관리되지 않는 API의 유니코드 버전을 사용하는 것이 좋습니다. 이렇게 하면 .NET Framework 문자열 개체의 네이티브 유니코드 형식에서 ANSI로 변환하는 데 따른 오버헤드를 방지할 수 있기 때문입니다.  
  
## PInvoke를 사용하지 말아야 할 조건  
 DLL의 모든 C 스타일 함수에 PInvoke를 사용하는 것이 적절하지 않습니다.  예를 들어 다음과 같이 선언된 MakeSpecial 함수가 mylib.dll에 있다고 가정해 봅시다.  
  
 `char * MakeSpecial(char * pszString);`  
  
 Visual C\+\+ 응용 프로그램에서 PInvoke를 사용하는 경우 다음과 비슷한 코드를 작성해야 합니다.  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 이 경우 MakeSpecial이 반환하는 관리되지 않는 문자열에 대한 메모리를 삭제할 수 없다는 문제가 있습니다.  PInvoke를 통해 호출되는 다른 함수는 사용자가 할당 취소할 필요가 없는 내부 버퍼에 대한 포인터를 반환합니다.  이 경우 IJW 기능을 사용하는 것이 좋습니다.  
  
## PInvoke의 제한 사항  
 매개 변수로 사용한 것과 동일한 포인터를 네이티브 함수에서 반환할 수 없습니다.  PInvoke를 사용하여 마샬링한 포인터를 네이티브 함수에서 반환하는 경우 메모리가 충돌하고 예외가 발생할 수 있습니다.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 다음 샘플에서는 이 문제를 보여 줍니다. 프로그램이 올바른 결과를 출력하는 것처럼 보일 수 있으나 이 출력은 할당 취소된 메모리에서 생성됩니다.  
  
```  
// platform_invocation_services_5.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
#include <limits.h>  
  
ref struct MyPInvokeWrap {  
public:  
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]  
   static String^ CharLower([In, Out] String ^);  
};  
  
int main() {  
   String ^ strout = "AabCc";  
   Console::WriteLine(strout);  
   strout = MyPInvokeWrap::CharLower(strout);  
   Console::WriteLine(strout);  
}  
```  
  
## 마샬링 인수  
 `PInvoke`를 사용하면 형태가 동일한 관리되는 형식과 C\+\+ 네이티브 기본 형식 사이에 마샬링할 필요가 없습니다.  예를 들어 Int32와 int 또는 Double과 double 사이에는 마샬링이 필요하지 않습니다.  
  
 그러나 형태가 동일하지 않은 형식은 마샬링해야 합니다.  여기에는 char, string 및 struct 형식이 포함됩니다.  다음 표서에는 다양한 형식에 대해 마샬러에 사용되는 매핑이 나와 있습니다.  
  
|wtypes.h|Visual C\+\+|\/CLR을 사용한 Visual C\+\+|공용 언어 런타임|  
|--------------|------------------|-----------------------------|---------------|  
|HANDLE|void\*|void\*|IntPtr, UIntPtr|  
|BYTE|unsigned char|unsigned char|Byte|  
|SHORT|short|short|Int16|  
|WORD|unsigned short|unsigned short|UInt16|  
|INT|int|int|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|LONG|long|long|Int32|  
|BOOL|long|bool|Boolean|  
|DWORD|unsigned long|unsigned long|UInt32|  
|ULONG|unsigned long|unsigned long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|char\*|String ^ \[in\], StringBuilder ^ \[in, out\]|String ^ \[in\], StringBuilder ^ \[in, out\]|  
|LPCSTR|const char \*|String ^|String|  
|LPWSTR|wchar\_t\*|String ^ \[in\], StringBuilder ^ \[in, out\]|String ^ \[in\], StringBuilder ^ \[in, out\]|  
|LPCWSTR|const wchar\_t \*|String ^|String|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|Double|  
  
 해당 주소가 관리되지 않는 함수에 전달되는 경우 마샬러는 런타임 힙에 할당된 메모리를 자동으로 고정합니다.  메모리를 고정하면 가비지 수집기가 압축을 진행하는 동안 메모리의 할당된 블록을 옮길 수 없습니다.  
  
 이 항목의 앞부분에 나와 있는 예제에서 DllImport의 CharSet 매개 변수는 관리되는 String을 마샬링하는 방법을 지정합니다. 이 경우 String은 네이티브 측에 대해 ANSI 문자열로 마샬링됩니다.  
  
 MarshalAs 특성을 사용하여 네이티브 함수의 개별 인수에 대한 마샬링 정보를 지정할 수 있습니다.  String \* 인수를 마샬링하는 데는 BStr, ANSIBStr, TBStr, LPStr, LPWStr 및 LPTStr 중에서 선택할 수 있습니다.  기본값은 LPStr입니다.  
  
 이 예제에서 문자열은 더블바이트 유니코드 문자열 LPWStr로 마샬링됩니다.  마샬링된 문자열의 두 번째 바이트가 null이고 puts가 이를 문자열 끝 마커로 해석하기 때문에 출력은 Hello World\!의 첫 번째 문자입니다.  
  
```  
// platform_invocation_services_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", EntryPoint="puts")]  
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 MarshalAs 특성은 System::Runtime::InteropServices 네임스페이스에 있습니다.  이 특성은 배열 같은 다른 데이터 형식과 함께 사용할 수 있습니다.  
  
 이 항목의 앞부분에서 언급했듯이 마샬링 라이브러리는 네이티브 및 관리 환경 사이에 데이터를 마샬링할 수 있는 새로운 최적의 방법을 제공합니다.  자세한 내용은 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)을 참조하십시오.  
  
## 성능 고려 사항  
 PInvoke는 한 번 호출할 때마다 10개에서 30개의 x86 명령을 실행하는 오버헤드가 발생합니다.  이러한 고정적인 성능 비용 이외에도 마샬링을 사용하면 오버헤드가 추가로 발생합니다.  관리 코드와 비관리 코드에서 표현이 동일한 blittable 형식 사이에는 마샬링에 따른 성능 저하가 없습니다.  예를 들어, int와 Int32 사이에 변환하는 경우에는 성능이 저하되지 않습니다.  
  
 성능을 향상시키려면 한 번 호출할 때 데이터를 더 적게 마샬링하는 호출을 많이 사용하는 대신 최대한 많은 데이터를 마샬링하는 PInvoke 호출을 적게 사용해야 합니다.  
  
## 참고 항목  
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)