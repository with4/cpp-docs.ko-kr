---
title: '방법:-clr로 마이그레이션: 안전 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- migration [C++], verifiable assemblies
- upgrading Visual C++ applications, verifiable assemblies
- verifiable assemblies [C++], migrating to
- /clr compiler option [C++], migrating to /clr:safe
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d72be19eb893a74a17a988e8c14c6bdaba766cbc
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704516"
---
# <a name="how-to-migrate-to-clrsafe-ccli"></a>방법: /clr:safe로 마이그레이션(C++/CLI)

> [!IMPORTANT]
> **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다. CLR 어셈블리를 안전 하 게 보호 해야 할 경우에 C# 코드를 포팅하는 것이 좋습니다.

이전 버전의 Visual Studio 2017 전에 Visual c + + 컴파일러 도구를 사용 하는 경우 사용 하 여 확인할 수 있는 구성 요소를 생성할 수 있습니다 **/clr: safe**, 각각에 대 한 오류를 생성 합니다. 컴파일러가 비안정형 코드 생성 개체입니다.

## <a name="remarks"></a>설명

다음과 같은 문제가 검증 가능성 오류를 생성합니다.

- 네이티브 형식입니다. 사용 되지 않는 경우에 네이티브 클래스, 구조체, 포인터 또는 배열 선언의 컴파일 수 없게 됩니다.

- 전역 변수

- 공용 언어 런타임 함수 호출 등 모든 관리 되지 않는 라이브러리에 대 한 함수

- 확인할 수 있는 함수를 포함할 수 없습니다는 [static_cast 연산자](../cpp/static-cast-operator.md) 다운 캐스팅 합니다. [static_cast 연산자](../cpp/static-cast-operator.md) 사용할 수에 대 한 기본 형식 간의 캐스팅 있지만 다운 캐스팅 [safe_cast](../windows/safe-cast-cpp-component-extensions.md) 또는 C 스타일 캐스트 (으로 구현 되는 한 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)) 사용 해야 합니다.

- 확인할 수 있는 함수를 포함할 수 없습니다는 [reinterpret_cast Operator](../cpp/reinterpret-cast-operator.md) (또는 모든 C 스타일 캐스트에 해당).

- 안정형 함수에서 산술 연산을 수행할 수 없습니다는 [interior_ptr (C + + /cli CLI)](../windows/interior-ptr-cpp-cli.md)합니다. 여기에 할당 및 역참조만 될 수 있습니다.

- 안정형 함수 수 throw 하거나 값 형식 발생 하기 전에 boxed 수 있어야 하므로 참조 형식에 대 한 포인터를 catch 합니다.

- 안정형 함수만 확인할 수 있는 함수를 호출할 수 있습니다 (공용 언어 런타임에 대 한 호출을 허용 하지 않는 되도록 포함 `AtEntry` / `AtExit`, 있고는 따라서).

- 확인할 수 있는 클래스를 사용할 수 없습니다 <xref:System.Runtime.InteropServices.LayoutKind>합니다.

- Main 함수 이므로 모든 매개 변수를 선언할 수 없습니다 EXE를 작성 하는 경우 <xref:System.Environment.GetCommandLineArgs%2A> 명령줄 인수를 검색 하는 데 사용 해야 합니다.

- 가상 호출 하는 가상 함수입니다. 예를 들어:

   ```cpp
   // not_verifiable.cpp
   // compile with: /clr
   ref struct A {
      virtual void Test() {}
   };

   ref struct B : A {};

   int main() {
      B^ b1 = gcnew B;
      b1->A::Test();   // Non-virtual call to virtual function
   }
   ```

또한 다음 키워드는 검증할 수 있는 코드에서 사용할 수 없습니다.

- [관리 되지 않는](../preprocessor/managed-unmanaged.md) 및 [팩](../preprocessor/pack.md) pragma

- [naked](../cpp/naked-cpp.md) 및 [맞춤](../cpp/align-cpp.md) [__declspec](../cpp/declspec.md) 한정자

- [__asm](../assembler/inline/asm.md)

- [__based](../cpp/based-grammar.md)

- [__try](../cpp/try-except-statement.md) 및 `__except`

## <a name="see-also"></a>참고자료

- [순수형 및 안정형 코드(C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
