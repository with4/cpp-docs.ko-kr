---
title: C + + Interop (암시적 PInvoke)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a095f252c4e46e212e42a7ab4cf3cb8d5ef6f53d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704295"
---
# <a name="using-c-interop-implicit-pinvoke"></a>C++ Interop 사용(암시적 PInvoke)

다른.NET 언어와 달리 Visual c + +에서는 동일한 응용 프로그램 및 동일한 파일에도 존재 하는 관리 및 비관리 코드를 허용 하는 상호 운용성 지원 (으로 [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md) pragma). Visual c + + 개발자를 응용 프로그램의 나머지 부분을 방해 하지 않고 기존 Visual c + + 응용 프로그램에.NET 기능을 통합할 수 있습니다.

사용 하 여 관리 되는 compiland에서 관리 되지 않는 함수를 호출할 수도 [dllexport, dllimport](../cpp/dllexport-dllimport.md)합니다.

암시적 PInvoke 방법을 함수 매개 변수를 마샬링하는, 또는 DllImportAttribute 명시적으로 호출 하는 경우 지정할 수 있는 다른 세부 정보를 지정 해야 하는 경우에 유용 합니다.

Visual c + +에서는 두 가지 방법으로 상호 운용 하도록 스레드와 관리 되지 않는 함수를 제공 합니다.

- [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

명시적 PInvoke에는.NET Framework에서 지원 되며 대부분의.NET 언어에서 사용할 수 있는 합니다. 하지만 c + + Interop를 Visual c + + 관련 이름에서 알 수 있듯이 합니다.

## <a name="c-interop"></a>C++ Interop

C + + Interop 것이 좋습니다 명시적 구현 하려면 일반적으로 번거로운, 관리 되지 않는 API를 수정 하 고 사용 가능 하지 않은 성능 향상 가능한 명시적 하면 경우 폭이 넓어서 더 더 나은 형식 안전성을 제공 하기 때문에 PInvoke입니다. 그러나 c + + Interop는 관리 되지 않는 소스 코드를 사용할 수 없는 경우에 수는 없습니다.

## <a name="c-com-interop"></a>C++ COM Interop

COM 구성 요소와의 상호 운용에 관한 다른.NET 언어에 비해 특정 뛰어난을 제공 하는 Visual c + +에서 지 원하는 상호 운용성 기능입니다. .NET Framework의 제한으로 제한 하지 않고 [Tlbimp.exe (형식 라이브러리 가져오기)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), COM을 사용 하면 c + + Interop 예: 데이터 형식 및 모든 COM 인터페이스의 모든 멤버의 필수 노출에 대 한 제한 된 지원 구성 요소에서 액세스할 수 되며 별도 interop 어셈블리를 필요 하지 않습니다. Visual Basic 및 C#에서는 달리 Visual c + +는 일반적인 COM 메커니즘을 사용 하 여 직접 COM 개체를 사용할 수 있습니다 (같은 **CoCreateInstance** 및 **QueryInterface**). 이 c + + Interop 기능을 사용 하면 컴파일러가 자동으로 관리 되지 않는 관리 되는 함수를 이동 하 고 복귀 하는 전환 코드를 삽입 되기 때문에 가능 합니다.

C + + Interop를 사용 하 여 COM 구성 요소도 사용할 수 일반적으로 사용 되는 또는 c + + 클래스 내 줄 바꿈할 수 있습니다. 이러한 래퍼 클래스를 사용자 지정 런타임 호출 가능 래퍼 라고 나 간단히 줄여 Crcw, 있으며 COM 응용 프로그램 코드에서 직접 사용 하 여 다음 두 가지 장점이:

- Visual c + + 이외의 언어에서 결과 클래스를 사용할 수 있습니다.

- 관리 되는 클라이언트 코드에서 COM 인터페이스의 세부 정보를 숨길 수 있습니다. .NET 데이터 형식을 기본 형식 대신 사용할 수 있습니다 및 내용을 CRCW 내 데이터 마샬링을의 세부 정보를 투명 하 게 수행할 수 있습니다.

COM 사용할 직접적으로 또는 한 CRCW 통해, 단순, blittable 형식 이외의 다른 인수 형식은 마샬링되어야 합니다.

## <a name="blittable-types"></a>Blittable 형식

간단 하 고 내장 형식을 사용 하는 관리 되지 않는 Api에 대 한 (참조 [blittable 형식 및 비 Blittable 형식](/dotnet/framework/interop/blittable-and-non-blittable-types)), 특별 한 코딩이 메모리에 표현이 동일한 이러한 데이터 형식을 더 복잡 한 데이터 형식은 필요 하기 때문에 필요 마샬링 명시적 데이터입니다. 예를 들어 참조 [하는 방법: 관리 되는 코드를 사용 하 여 PInvoke에서 네이티브 Dll 호출](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)합니다.

## <a name="example"></a>예

```cpp
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

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>섹션 내용

- [방법: C++ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 구조체 마샬링](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 배열 마샬링](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 콜백 및 대리자 마샬링](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 포함 포인터 마샬링](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [방법: System::String의 문자에 액세스](../dotnet/how-to-access-characters-in-a-system-string.md)

- [방법: char * 문자열을 System::Byte 배열로 변환](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [방법: system:: string을 wchar_t * 또는 char로 변환\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [방법: System::String을 표준 문자열로 변환](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [방법: 표준 문자열을 System::String으로 변환](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [방법: 바이트 배열에 대한 포인터 가져오기](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [방법: 관리되지 않는 리소스를 바이트 배열로 로드](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [방법: 네이티브 함수에서 참조 클래스 수정](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [방법: 이미지가 네이티브인지 CLR인지 확인](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [방법: 전역 어셈블리 캐시에 네이티브 DLL 추가](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [방법: 값 형식에 대한 참조를 네이티브 형식에 저장](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [방법: 관리되지 않는 메모리에 개체 참조 유지](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [방법: /clr 컴파일 감지](../dotnet/how-to-detect-clr-compilation.md)

- [방법: System::Guid 및 _GUID 사이에 변환](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [방법: out 매개 변수 지정](../dotnet/how-to-specify-an-out-parameter.md)

- [방법: /clr 컴파일에 네이티브 형식 사용](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)

- [방법: C#에서 사용하기 위해 네이티브 클래스 래핑](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Interop 시나리오에서 대리자를 사용 하는 방법은 참조 하십시오. [대리자 (c + + 구성 요소 확장명)](../windows/delegate-cpp-component-extensions.md)합니다.

## <a name="see-also"></a>참고자료

- [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)
