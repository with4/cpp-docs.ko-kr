---
title: "/Zc:throwingNew (가정 연산자 새 throw) | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- throwingNew
- /Zc:throwingNew
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cbcb635cd37a40c2de1599d271658de308e8cff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc:throwingNew (가정 연산자 새 throw)  
경우는 `/Zc:throwingNew` 옵션을 지정 하면 컴파일러 최적화에 대 한 호출 `operator new` 반환 null 포인터에 대 한 검사를 건너뜁니다. 이 옵션으로 모든 링크의 구현 된 생각 하는 컴파일러가 `operator new` 및 사용자 지정 할당자를 사용 하면 c + + 표준을 준수 하 고 할당 실패 시 throw 합니다. 기본적으로 Visual Studio에서 컴파일러 pessimistically 생성 null 검사 (`/Zc:throwingNew-`) 호출에 대 한 이러한, 사용자가 throw 되지 않는 구현에 연결할 수 있으므로 `operator new` 하거나 null 포인터를 반환 하는 사용자 지정 할당자 루틴을 작성 합니다.  
  
## <a name="syntax"></a>구문  
  
`/Zc:throwingNew`[`-`]  
  
## <a name="remarks"></a>설명  
  
ISO C + + 98 이후 표준이 지정 하는 기본 [new 연산자](../../standard-library/new-operators.md#op_new) throw `std::bad_alloc` 메모리 할당에 실패 한 경우. Visual Studio 6.0까지 Visual c + +의 버전이 할당 실패에 null 포인터를 반환 합니다. Visual Studio 2002 년부터 `operator new` 표준을 준수 하 고 실패 시 throw 합니다. 이전 할당 스타일을 사용 하는 코드를 지원 하기 위해 Visual Studio는 linkable 구현을 제공 `operator new` 에 *nothrownew.obj와 연결* 실패 시 null 포인터를 반환 하는 합니다. 기본적으로 컴파일러는 또한 방어 null 검사를 실패 한 경우 즉시 충돌을 일으키는 이전 스타일 할당자를 사용 하면 이러한를 생성 합니다. `/Zc:throwingNew` 있으면 이러한 null 검사를 생략 컴파일러 옵션, 메모리를 연결 되어 있음을 가정에 할당자를 사용 하면 표준을 준수 합니다. 명시적 throw 되지 않는에 적용 되지 않습니다 `operator new` 형식의 추가 매개 변수를 사용 하 여 선언 된 오버 로드 `std::nothrow_t` 명시적 있고 `noexcept` 사양입니다.  
  
개념적으로 메모리를 할당 하는 코드 생성 컴파일러의 사용 가능한 저장소에서 개체를 만들려고 다음 메모리를 초기화 하는 생성자를 호출 합니다. 일반적으로 Visual c + + 컴파일러에 맞지 않는, throw 되지 않는 할당자를이 코드는 연결 하는 경우 알 수 없습니다, 때문에 기본적으로도 생성 생성자를 호출 하기 전에 null 검사 합니다. Null 포인터를 이렇게 throw 되지 않는 할당에 실패 하면 생성자 호출에 역참조 합니다. 대부분의 경우에서 이러한 확인 작업이 필요 하기 때문에 기본 `operator new` 할당자를 사용 하면 null 포인터를 반환 하는 대신 throw 합니다. 검사 든 부작용을 갖게 됩니다. 코드 크기를 팽창이 하 고 분기 예측자를 넘쳐나 devirtualization 또는 const 전파 하 여 초기화 된 개체에서와 같은 다른 유용한 컴파일러 최적화를 금지 합니다. 지원 링크 되는 코드에만 존재 하는 검사 *nothrownew.obj와 연결* 되었거나 사용자 지정 맞지 않는 `operator new` 구현 합니다. 비준수를 사용 하지 않는 경우 `operator new`를 사용 하는 것이 좋습니다 `/Zc:throwingNew` 코드를 최적화할 수 있습니다.  
  
링크 타임 코드 생성 LTCG ()를 사용 하 여 컴파일하는 경우 지정할 필요가 없습니다 `/Zc:throwingNew`합니다. LTCG를 사용 하 여 코드를 컴파일할 때 컴파일러 있는지 확인 하는 기본 준수 `operator new` 구현이 사용 됩니다. 이 경우 컴파일러가 생략 하는 null 검사 자동으로 합니다. 링커 검색는 `/ThrowingNew` 구별 하는 플래그 경우의 구현 `operator new` 준수 됩니다. 사용자 지정 연산자 새 구현에 대 한 원본에서이 지시어를 포함 하 여 링커에이 플래그를 지정할 수 있습니다.  
  
```cpp  
#pragma comment(linker, "/ThrowingNew")  
```  
  
Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
2.  **구성을** 드롭다운 메뉴에서 선택 **모든 구성**합니다.  
3.  선택 된 **구성 속성**, **C/c + +**, **명령줄** 속성 페이지.  
4.  수정 된 **추가 옵션** 포함할 속성을 `/Zc:throwingNew` 또는 `/Zc:throwingNew-` 선택한 후 **확인**합니다.  
  
## <a name="see-also"></a>참고 항목  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
[/Zc (규칙)](../../build/reference/zc-conformance.md)  
[noexcept(C++)](../../cpp/noexcept-cpp.md)  
[예외 사양(throw)(C++)](../../cpp/exception-specifications-throw-cpp.md)  
[(예외)를 종료 합니다.](../../standard-library/exception-functions.md#terminate)  
