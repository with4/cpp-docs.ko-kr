---
title: 링커 입력 파일로.netmodule 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbb2ab74e8c9d0285b9bec2f9979257d89797022
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704567"
---
# <a name="netmodule-files-as-linker-input"></a>링커 입력 파일로 사용하는 .netmodule 파일

link.exe에서는 이제 MSIL .obj 및 .netmodules가 입력으로 사용됩니다. 링커에 의해 생성 된 출력 파일이 어셈블리 또는.obj 또는 링커로 입력 된.netmodules에 런타임에 의존 하지 않고.netmodule 합니다.

Visual c + + 컴파일러에 의해.netmodules 만들어집니다 [/LN (MSIL 모듈 만들기)](../../build/reference/ln-create-msil-module.md) 또는 사용 하 여 링커에 의해 [/NOASSEMBLY (MSIL 모듈 만들기)](../../build/reference/noassembly-create-a-msil-module.md)합니다. .obj Visual c + + 컴파일에서 항상 생성 됩니다. 다른 Visual Studio 컴파일러에 대 한 사용는 **/target: module** 컴파일러 옵션입니다.

전달 해야 링커에.obj 파일을.netmodule를 만든 Visual c + + 컴파일에서에서. .Netmodule를 전달 하기 때문에 더 이상 지원 되지는 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

명령줄에서 링커를 실행 하는 방법에 대 한 정보를 참조 하십시오. [링커 명령줄 구문](../../build/reference/linker-command-line-syntax.md), [명령줄에서 빌드 C/c + + 코드](../../build/building-on-the-command-line.md), 및 [경로 및 환경 변수 설정 명령줄 빌드](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

Visual c + + 컴파일러에 의해 컴파일된 링커에.netmodule 또는.dll 파일을 전달 **/clr** 링커 오류가 발생할 수 있습니다. 자세한 내용은 참조 [.netmodule 입력 파일 형식을 선택 한다는](../../build/reference/choosing-the-format-of-netmodule-input-files.md)합니다.

로 컴파일된 MSIL.obj 파일 뿐 아니라 네이티브.obj 파일 링커에서 **/clr**합니다. 동일한 빌드에서 혼합된.obj로 전달할 때 결과 출력 파일의 검증 가능성, 기본적으로와 같게 됩니다 입력된 모듈의 가장 낮은 수준입니다.

현재 두 개 이상의 어셈블리로 구성된 응용 프로그램이 있고 이 응용 프로그램을 하나의 어셈블리에 포함하려면 어셈블리를 다시 컴파일한 후 .objs 또는 .netmodules를 링크하여 단일 어셈블리를 생성해야 합니다.

사용 하 여 항목을 지정 해야 [/ENTRY (진입점 기호)](../../build/reference/entry-entry-point-symbol.md) 실행 가능 이미지를 만들 때.

MSIL.netmodule 또는.obj 파일을 연결 하는 경우 사용 [/LTCG (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md), 그렇지 않은 경우 링커는 MSIL.obj 또는.netmodule를 발견 하면 다시 시작 됩니다 /LTCG을 링크 합니다.

MSIL .obj 또는 .netmodule 파일은 cl.exe로도 전달할 수 있습니다.

입력 MSIL .obj 또는 .netmodule 파일은 포함된 리소스를 가질 수 없습니다. 리소스 사용 (모듈 또는 어셈블리) 출력 파일에 포함 된 [하지만 (관리 되는 리소스 포함)](../../build/reference/assemblyresource-embed-a-managed-resource.md) 링커 옵션 또는 **/resource** 다른 Visual Studio 컴파일러에서 컴파일러 옵션입니다.

MSIL 링크를 수행 하는 경우 및도 지정 하지 않으면 [/LTCG (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md), 링크를 다시 시작 정보 메시지가 표시 됩니다. 이 메시지를 msil 링크 링커 성능이 향상 되지만 무시, 명시적으로 지정 **/LTCG**합니다.

## <a name="example"></a>예

C + + 코드에서는 **catch** 해당 블록 **시도** 비 시스템 예외에 대 한 호출 됩니다. 그러나 기본적으로 CLR 예외를 래핑합니다 비시스템와 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>합니다. 어셈블리는 Visual c + + 및 비-Visual c + + 모듈에서 만들어질 있고 하려는 경우는 **catch** c + + 코드를 호출 하면 해당에서 차단 **시도** 절 때는 **시도**추가 해야 블록 비 시스템 예외를 throw 하는 경우는 `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` 비 c + + 모듈에 대 한 소스 코드에 특성입니다.

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

## <a name="example"></a>예

부울 값을 변경 하 여는 `WrapNonExceptionThrows` Visual c + + 코드의 비시스템 예외를 catch 하는 기능을 수정할 특성입니다.

```cpp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>참고자료

- [LINK 입력 파일](../../build/reference/link-input-files.md)
- [링커 옵션](../../build/reference/linker-options.md)
