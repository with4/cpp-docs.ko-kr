---
title: "C++ Interop 사용(암시적 PInvoke) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - ".NET[C++], C++ 네이티브 포팅"
  - "blittable 형식[C++]"
  - "C++ COM Interop"
  - "C++ Interop"
  - "C++, interop"
  - "COM 인터페이스[C++]"
  - "데이터 마샬링[C++], C++ Interop 기능"
  - "예제[C++], 상호 운용성"
  - "암시적 플랫폼 호출"
  - "interop[C++], 기능"
  - "상호 운용성[C++]"
  - "상호 운용성[C++], 암시적 PInvoke"
  - "마샬링[C++], C++ Interop 기능"
  - "플랫폼 호출[C++], 예제"
  - "플랫폼 호출[C++], implicit"
  - "이식[C++], C++ 네이티브를 .NET으로"
  - "형식[C++], blittable"
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ Interop 사용(암시적 PInvoke)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 .NET 언어와 달리 Visual C\+\+에서 지원하는 상호 운용성을 활용하면 관리 코드와 비관리 코드를 동일한 응용 프로그램에 배치할 수 있고, [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) pragma를 사용하여 동일한 파일에 배치할 수도 있습니다.  Visual C\+\+ 개발자는 이러한 상호 운용성을 통해 응용 프로그램의 나머지 부분은 그대로 유지한 채 .NET 기능을 기존 Visual C\+\+ 응용 프로그램에 통합할 수 있습니다.  
  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)를 사용하여 관리되는 컴파일 대상에서 관리되지 않는 함수를 호출할 수도 있습니다.  
  
 암시적 PInvoke는 함수 매개 변수를 마샬링하는 방식을 지정할 필요가 없거나 DllImportAttribute를 명시적으로 호출할 때 지정할 수 있는 다른 세부 정보를 지정할 필요가 없는 경우에 유용합니다.  
  
 Visual C\+\+에서는 두 가지 방법으로 관리되는 함수와 관리되지 않는 함수를 상호 운용할 수 있습니다.  
  
-   [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
 명시적 PInvoke는 .NET Framework에서 지원하며 대부분의 .NET 언어에서 사용할 수 있습니다.  그러나 그 이름에서 알 수 있듯이 C\+\+ Interop는 Visual C\+\+에서만 사용할 수 있습니다.  
  
## C\+\+ Interop  
 C\+\+ Interop는 형식이 더 안전하고, 일반적으로 더 손쉽게 구현할 수 있으며, 관리되지 않는 API를 수정해도 더 많은 융통성을 발휘할 수 있고, 명시적 PInvoke로는 얻을 수 없는 성능 향상을 꾀할 수 있다는 점에서 명시적 PInvoke보다 많은 이점이 있습니다.  그러나 관리되지 않는 소스 코드를 사용할 수 없거나 **\/clr:safe**를 사용하여 컴파일하는 경우에는 C\+\+ Interop를 사용할 수 없습니다. 자세한 내용은 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)를 참조하십시오.  
  
## C\+\+ COM Interop  
 Visual C\+\+에서 지원하는 상호 운용성 기능을 사용하면 COM 구성 요소에 대한 상호 운용 작업을 수행할 때 다른 .NET 언어에 비해 특별한 이점을 얻을 수 있습니다.  모든 COM 인터페이스의 각 멤버를 반드시 노출해야 한다거나 데이터 형식이 제한적으로 지원되는 등, .NET Framework [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)에 적용되는 제한 사항에 구애받지 않은 채, C\+\+ Interop를 사용하면 언제든지 COM 구성 요소에 액세스할 수 있고 별도의 interop 어셈블리를 사용할 필요도 없습니다.  자세한 내용은 [Using COM from .NET](http://msdn.microsoft.com/ko-kr/03976661-6278-4227-a6c1-3b3315502c15)을 참조하십시오.  
  
## Blittable 형식  
 단순한 내장 형식\([Blittable 형식 및 비 Blittable 형식](../Topic/Blittable%20and%20Non-Blittable%20Types.md) 참조\)을 사용하는 관리되지 않는 API의 경우 특별한 코딩이 필요하지 않습니다. 이러한 데이터 형식의 경우 메모리에 동일한 표현이 있기 때문입니다. 그러나 더 복잡한 데이터 형식의 경우에는 명시적인 데이터 마샬링이 필요합니다.  예제를 보려면 [방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)를 참조하십시오.  
  
## 예제  
  
```  
// vcmcppv2_impl_dllimp.cpp  
// compile with: /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
// Implicit DLLImport specifying calling convention  
extern "C" int __stdcall MessageBeep(int);  
  
// explicit DLLImport needed here to use P/Invoke marshalling because  
// System::String ^ is not the type of the first parameter to printf  
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]  
// or just  
// [DllImport("msvcrt.dll")]  
int printf(System::String ^, ...);   
  
int main() {  
   // (string literals are System::String by default)  
   printf("Begin beep\n");  
   MessageBeep(100000);  
   printf("Done\n");  
}  
```  
  
  **경고음 시작**  
**완료**   
## 단원 내용  
  
-   [방법: C\+\+ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 구조체 마샬링](../dotnet/how-to-marshal-structures-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 배열 마샬링](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 콜백 및 대리자 마샬링](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
-   [방법: C\+\+ Interop를 사용하여 포함 포인터 마샬링](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)  
  
-   [방법: System::String의 문자에 액세스](../dotnet/how-to-access-characters-in-a-system-string.md)  
  
-   [방법: char \* 문자열을 System::Byte 배열로 변환](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)  
  
-   [방법: System::String을 wchar\_t\* 또는 char\*로 변환](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)  
  
-   [방법: System::String을 표준 문자열로 변환](../dotnet/how-to-convert-system-string-to-standard-string.md)  
  
-   [방법: 표준 문자열을 System::String으로 변환](../dotnet/how-to-convert-standard-string-to-system-string.md)  
  
-   [방법: 바이트 배열에 대한 포인터 가져오기](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)  
  
-   [방법: 관리되지 않는 리소스를 바이트 배열로 로드](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)  
  
-   [방법: 네이티브 함수에서 참조 클래스 수정](../dotnet/how-to-modify-reference-class-in-a-native-function.md)  
  
-   [방법: 이미지가 네이티브인지 CLR인지 확인](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)  
  
-   [방법: 전역 어셈블리 캐시에 네이티브 DLL 추가](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)  
  
-   [방법: 값 형식에 대한 참조를 네이티브 형식에 저장](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)  
  
-   [방법: 관리되지 않는 메모리에 개체 참조 유지](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)  
  
-   [방법: \/clr 컴파일 감지](../dotnet/how-to-detect-clr-compilation.md)  
  
-   [방법: System::Guid 및 \_GUID 사이에 변환](../dotnet/how-to-convert-between-system-guid-and-guid.md)  
  
-   [방법: out 매개 변수 지정](../dotnet/how-to-specify-an-out-parameter.md)  
  
-   [방법: \/clr 컴파일에 네이티브 형식 사용](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)  
  
-   [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)  
  
-   [방법: C\#에서 사용하기 위해 네이티브 클래스 래핑](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
 interop 시나리오에서 대리자를 사용하는 방법에 대한 자세한 내용은 [delegate](../windows/delegate-cpp-component-extensions.md)를 참조하십시오.  
  
## 참고 항목  
 [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)