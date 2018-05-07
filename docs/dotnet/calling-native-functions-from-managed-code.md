---
title: 관리 코드에서 네이티브 함수 호출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c0d7e69c95790122f44dc59d06f2843afbddfb2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="calling-native-functions-from-managed-code"></a>관리 코드에서 네이티브 함수 호출
공용 언어 런타임 관리 수 있게 네이티브 동적 연결 라이브러리 (Dll)의 C 스타일 함수를 호출 하는 코드는 PInvoke 또는 플랫폼 호출 서비스를 제공 합니다. 런타임 및 것 바로 "작동", 또는 IJW, 메커니즘에 대 한 COM 상호 운용성의 경우와 동일한 데이터 마샬링 사용 됩니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [플랫폼 호출 자세히 보기](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 이 섹션의에서 예제에서는 대해서만 설명 방법을 `PInvoke` 사용할 수 있습니다. `PInvoke` 프로시저 마샬링 코드를 작성 하는 대신 특성에 선언적으로 마샬링 정보를 제공 하기 때문에 사용자 지정 된 데이터 마샬링을 간소화할 수 있습니다.  
  
> [!NOTE]
>  마샬링 라이브러리는 최적화 된 방식으로 네이티브 및 관리 환경 간에 데이터를 마샬링해야 하는 대체 방법을 제공 합니다. 참조 [개요의 c + + 마샬링](../dotnet/overview-of-marshaling-in-cpp.md) 마샬링 라이브러리에 대 한 자세한 내용은 합니다. 마샬링 라이브러리를 데이터에만 및 함수에 대 한 사용할 수 있습니다.  
  
## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke와 DllImport 특성  
 다음 예제에서는 사용을 보여 줍니다. `PInvoke` Visual c + + 프로그램에서 합니다. 네이티브 함수는 msvcrt.dll에 정의 됩니다. DllImport 특성은 선언에 사용 됩니다.  
  
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
  
 다음 샘플 앞의 예와 동일 하지만 IJW 사용 합니다.  
  
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
  
### <a name="advantages-of-ijw"></a>IJW의 장점  
  
-   쓸 필요가 없습니다 `DLLImport` 프로그램 사용 하 여 관리 되지 않는 Api에 대 한 선언을 특성입니다. 헤더 파일 및 링크는 가져오기 라이브러리만 포함 됩니다.  
  
-   IJW 메커니즘은 약간 더 빠르며 (예를 들어 IJW 스텁이 필요 하지 않은 하는 개발자가 명시적으로 수행 되기 때문에 필요가 pin 또는 복사 데이터 항목에 대 한 확인).  
  
-   명확 하 게 성능 문제를 보여 줍니다. 이 경우 ANSI 문자열을 해당 하는 유니코드 문자열에서 번역 하 고 있다는 사실을 점과 메모리 할당 및 할당 취소 했습니다. IJW를 사용 하 여 코드를 작성 하는 개발자 호출을 실제로이 경우 `_putws` 를 사용 하 여 및 `PtrToStringChars` 성능이 향상 될 것입니다.  
  
-   전달을 한 번에 많은 관리 되지 않는 Api 동일한 데이터를 마샬링하기를 호출 하는 경우 마샬링된 복사본 될 때마다 다시 마샬링 보다 훨씬 더 효율적입니다.  
  
### <a name="disadvantages-of-ijw"></a>IJW의 단점  
  
-   마샬링 지정 되어야 합니다 명시적으로 대신 코드에서 특성 (종종를 포함 하는 적절 한 기본값).  
  
-   마샬링 코드는 응용 프로그램 논리의 흐름에서 더 침투 적 하는 인라인 합니다.  
  
-   명시적 마샬링 Api 반환 하므로 `IntPtr` 32 비트에서 64 비트 이식성에 대 한 형식 추가로 사용 해야 `ToPointer` 호출 합니다.  
  
 C + +에 의해 노출 되는 특정 메서드는 더 효율적이 고 명시적 메서드 코드가 더 복잡해 몇 가지 단점이 있습니다.  
  
 응용 프로그램에는 주로 관리 되지 않는 데이터 형식을 사용 하거나.NET Framework Api 보다 더 관리 되지 않는 Api를 호출 하는 경우 것을 권장 합니다 IJW 기능을 사용 합니다. 대부분의 관리 되는 응용 프로그램에서 가끔 나타나는 관리 되지 않는 API를 호출 하려면 선택은 더 복잡 한 경우도 있습니다.  
  
## <a name="pinvoke-with-windows-apis"></a>Windows Api와 PInvoke  
 PInvoke는 Windows에서 함수 호출에 대 한 편리 합니다.  
  
 이 예제에서는 Visual c + + 프로그램 Win32 API의 일부인 MessageBox 함수 상호 운용 됩니다.  
  
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
  
 출력에는 제목이 PInvoke 테스트 하 고 Hello World 텍스트를 포함 하는 메시지 상자는!입니다.  
  
 마샬링 정보는 DLL에서 함수를 조회 하 여 PInvoke도 사용 됩니다. 에 user32.dll는 실제로 없지만 MessageBox 함수 CharSet = CharSet::Ansi 사용 PInvoke MessageBoxW 즉 유니코드 버전 대신 MessageBoxA, ANSI 버전을 사용 하도록 합니다. 일반적으로 ANSI로.NET Framework string 개체의 유니코드 네이티브 형식에서 오버 헤드가 번역은 제거 하는 관리 되지 않는 Api의 유니코드 버전을 사용 하는 것이 좋습니다.  
  
## <a name="when-not-to-use-pinvoke"></a>PInvoke를 사용 하지 않는 경우  
 PInvoke를 사용 하 여 Dll에서 모든 C 스타일 함수에 대해 적합 하지 않습니다. 예를 들어 있는 MakeSpecial mylib.dll의 함수를 다음과 같이 선언 됩니다.  
  
 `char * MakeSpecial(char * pszString);`  
  
 Visual c + + 응용 프로그램에서 PInvoke를 사용 하는 경우 다음과 유사한 코드를 작성 해야 합니다.  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 이 경우 makespecial 반환 되는 관리 되지 않는 문자열에 대 한 메모리 삭제할 수 없습니다. PInvoke를 통해 호출 하는 다른 함수는 사용자가 할당을 취소할 수 없는 내부 버퍼에 대 한 포인터를 반환 합니다. 이 경우 IJW 기능을 사용 하는 것이 좋습니다입니다.  
  
## <a name="limitations-of-pinvoke"></a>Pinvoke 제한 사항  
 매개 변수로 만든 네이티브 함수에서 동일한 포인터를 반환할 수 없습니다. PInvoke 여을 마샬링 한 포인터를 반환 하는 네이티브 함수를 예외와 메모리 손상 할 수 있습니다.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 다음 샘플에서는이 문제를 하 고 출력을 메모리에서 가져온 올바른 출력을 제공 하는 프로그램에 대 한 것, 경우에 합니다.  
  
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
  
## <a name="marshaling-arguments"></a>인수 마샬링  
 와 `PInvoke`, 마샬링할 필요가 없습니다 관리 되는 사이 같은 양식으로 c + + 네이티브 기본 형식입니다. 예를 들어 마샬링이 없는 Int32와 int 또는 Double 및 double 간에 필요 합니다.  
  
 그러나 같은 폼을 갖지 않는 형식은 마샬링해야 합니다. 여기에 문자, 문자열 및 구조체 형식이 포함 됩니다. 다음 표에서 다양 한 형식에 대 한 마샬러를 사용한 매핑을 보여 줍니다.  
  
|wtypes.h|Visual C++|/Clr을 사용한 visual c + +|공용 언어 런타임|  
|--------------|------------------|-----------------------------|-----------------------------|  
|HANDLE|void *|void *|IntPtr, UIntPtr|  
|BYTE|unsigned char|unsigned char|Byte|  
|SHORT|short|short|Int16|  
|WORD|unsigned short|unsigned short|UInt16|  
|INT|int|int|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|LONG|long|long|Int32|  
|BOOL|long|bool|부울|  
|DWORD|unsigned long|unsigned long|UInt32|  
|ULONG|unsigned long|unsigned long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|char *|String ^ [in], StringBuilder ^ [에, out]|String ^ [in], StringBuilder ^ [에, out]|  
|LPCSTR|const char *|String ^|문자열|  
|LPWSTR|wchar_t *|String ^ [in], StringBuilder ^ [에, out]|String ^ [in], StringBuilder ^ [에, out]|  
|LPCWSTR|const wchar_t *|String ^|문자열|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|Double|  
  
 마샬러가 자동으로 해당 주소는 관리 되지 않는 함수에 전달 되 면 런타임 힙에 할당 된 메모리를 고정 합니다. 고정 가비지 수집기를 압축 하는 동안 메모리의 할당된 된 블록을 이동할 수 없습니다.  
  
 이 항목의 앞부분에 나오는 예에서 DllImport의 CharSet 매개 변수 지정 방법을 관리 되는 문자열; 마샬링되어야 이 경우 기본 측에 대 한 ANSI 문자열을 마샬링할 수 해야 합니다.  
  
 MarshalAs 특성을 사용 하 여 네이티브 함수의 각 인수에 대 한 마샬링 정보를 지정할 수 있습니다. 문자열을 마샬링하기 위한 여러 가지 * 인수: BStr, ANSIBStr, TBStr, LPStr, LPWStr, 및 LPTStr 합니다. 기본값은 LPStr 합니다.  
  
 이 예제에서는 문자열을 더블 바이트 유니코드 문자 문자열로, LPWStr이 마샬링됩니다. 출력은 첫 글자의 Hello World! 마샬링된 문자열의 두 번째 바이트는 null이 고 배치 하기 때문에이 문자열의 끝 표식으로 해석 합니다.  
  
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
  
 MarshalAs 특성 System::Runtime::InteropServices 네임 스페이스에서입니다. 배열과 같은 다른 데이터 형식 특성을 사용할 수 있습니다.  
  
 이 항목의 앞부분에 나오는 설명 했 듯이 마샬링 라이브러리의 네이티브 및 관리 환경 간에 데이터를 마샬링하기 새로운 최적의 방법을 제공 합니다. 자세한 내용은 참조 [개요의 c + + 마샬링](../dotnet/overview-of-marshaling-in-cpp.md)합니다.  
  
## <a name="performance-considerations"></a>성능 고려 사항  
 PInvoke에 10과 30 사이의 오버 헤드를 x86 호출당 지시 합니다. 이 고정된 비용 외에도 마샬링 하면 오버 헤드가 추가로 합니다. 관리 코드와 비관리 코드에서 표현이 동일한 blittable 형식 일치 마샬링 비용이 부과 되지 않습니다. 예를 들어 int 및 Int32 사이 변환 하는 비용은 없습니다.  
  
 성능 향상을 위해 호출당 적은 양의 데이터를 마샬링하는 더 많은 호출 하는 대신 최대한 많은 데이터를 마샬링하는 더 적은 PInvoke 호출 했습니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)