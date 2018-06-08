---
title: 최적화에 대 한 유용한 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63d3437a08e3c8b69b564176e0f377566ab491e6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704242"
---
# <a name="optimization-best-practices"></a>최적화에 대 한 유용한 정보

이 문서에서는 Visual c + +에서 최적화에 대 한 몇 가지 모범 사례를 설명 합니다.

## <a name="compiler-and-linker-options"></a>컴파일러 및 링커 옵션

### <a name="profile-guided-optimization"></a>프로필 기반 최적화

Visual c + + 지원 *프로필 기반 최적화* (PGO). 이 최적화를 실행 하는 응용 프로그램의 뒷부분에 나오는 최적화의 프로필 데이터를 학습 실행 될 때 응용 프로그램의 계측된 된 버전을 사용 합니다. PGO 사용 시간이 걸릴 수, 모든 개발자가 사용 하는 문제가 않을 것 있지만 PGO를 사용 하 여 제품의 최종 릴리스 빌드에 대 한 권장지 않습니다. 자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다.

또한 *전체 프로그램 최적화* (링크 타임 코드 생성으로 알려져 있습니다) 및 **/O1** 및 **/O2** 최적화 향상 되었습니다. 일반적으로 이러한 옵션 중 하나를 사용 하 여 컴파일된 응용 프로그램은 이전 버전의 컴파일러를 사용 하 여 컴파일된 동일한 응용 프로그램 보다 더 빠릅니다 됩니다. 

자세한 내용은 참조 [/GL (전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md) 및 [/O1, /O2 (크기 최소화, 속도 최대화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)합니다.

### <a name="which-level-of-optimization-to-use"></a>사용 하는 최적화 수준

가능 하면 최종 릴리스 빌드 프로필 기반 최적화를 컴파일해야 합니다. 수 없으면 PGO, 함께 빌드되도록 인프라가 부족 하 여 계측 된 빌드를 실행 또는 시나리오에 액세스할 수 없는, 전체 프로그램 최적화 있는 건물을 제안 했습니다.

**/Gy** 스위치에도 매우 유용 합니다. 생성 되므로 링커에서 더 많은 유연성이 참조 되지 않은 Comdat 및 COMDAT 제거에 관한 각 함수에 대 한 별도 COMDAT 정리 합니다. 사용 하는 유일한 단점은 **/Gy** 디버깅 하는 경우 문제를 일으킬 수 있으므로 됩니다. 따라서 사용 하 여 일반적으로 좋습니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](../../build/reference/gy-enable-function-level-linking.md)를 참조하세요.

를 64 비트 환경에서 연결에 대 한 것이 좋습니다 사용 하는 **ICF, /opt: ref** 링커 옵션 및 32 비트 환경에서 **/opt: ref** 것이 좋습니다. 자세한 내용은 참조 [/OPT (최적화)](../../build/reference/opt-optimizations.md)합니다.

또한 강력한 최적화 된 릴리스 빌드 된 경우에 디버그 기호를 생성 하는 것이 좋습니다. 생성된 된 코드를 적용 하지 않습니다를 더 쉽게 하는 경우 응용 프로그램을 디버깅할 수 있도록 많은 수 있어야 합니다.

### <a name="floating-point-switches"></a>부동 소수점 스위치

**/Op** 컴파일러 옵션 제거 되 고 부동 소수점 최적화를 다루는 다음 4 개의 컴파일러 옵션이 추가 되었습니다.

|||
|-|-|
|**/fp: 정확 하 게**|기본 권장 사항을 이며 대부분의 경우에 사용 해야 합니다.|
|**/fp: fast**|예를 들어 게임에서에서 가장 중요 성능 인지 하는 것이 좋습니다. 보다 빠른 성능이 됩니다.|
|**/fp: strict**|권장 되는 경우 정확한 부동 소수점 예외 및 IEEE 동작이 필요 합니다. 이렇게 하면 성능이 가장 낮습니다.|
|**/fp: except [-]**|와 함께에서 사용할 수 있습니다 **/fp: strict** 또는 **/fp: 정확한**, 아닌 **/fp: fast**합니다.|

자세한 내용은 [/fp(부동 소수점 동작 지정)](../../build/reference/fp-specify-floating-point-behavior.md)를 참조하세요.

## <a name="optimization-declspecs"></a>최적화 declspec

이 섹션에서는 살펴보겠습니다 성능을 위해 프로그램에서 사용할 수 있는 두 개의 declspec: `__declspec(restrict)` 및 `__declspec(noalias)`합니다.

`restrict` declspec 등에 대 한 포인터를 반환 하는 함수 선언에만 적용할 수 있습니다 `__declspec(restrict) void *malloc(size_t size);`

`restrict` declspec 별칭이 지정 되지 않은 포인터를 반환 하는 함수에 사용 됩니다. 이 키워드는 C 런타임 라이브러리의 구현에 사용 됩니다 `malloc` 이후 이미 사용 중인 현재 프로그램의 (하지 않는 경우 해제 된 후에 메모리를 사용 하는 등 잘못 된 항목)는 포인터 값을 반환 하지 것입니다.

`restrict` declspec 컴파일러 최적화를 수행 하는 것에 대 한 자세한 정보는 컴파일러에 제공 합니다. 확인 하려면 컴파일러에 대 한 가장 까다로운 중 하나를 어떤 포인터 별칭 다른 포인터 이며 컴파일러를 사용 하면이 정보를 사용 하 여 크게입니다.

것은 의미가 지적 컴파일러 하지 것에 컴파일러는 확인 하기 위한 약속입니다. 프로그램이이 사용 하면 `restrict` declspec 프로그램 잘못 된 동작이 있을 수 있습니다, 부적절 하 게 합니다.

자세한 내용은 참조 [제한](../../cpp/restrict.md)합니다.

`noalias` declspec 함수에만 적용도 되 고 함수는 부분 순수 함수를 나타냅니다. 부분 순수 함수는 참조 하거나 지역 변수, 인수 및 인수 중 첫 번째 수준의 간접 참조를 수정 하는입니다. 이 declspec 컴파일러에 프라미스 이며 응용 프로그램을 중단 하는 함수가 전역 변수를 참조 하거나 차 간접 참조 포인터 인수는 컴파일러의 코드를 생성할 수 있습니다.

자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.

## <a name="optimization-pragmas"></a>최적화 pragma

코드 최적화에 대 한 몇 가지 유용한 pragma도 있습니다. 아래에서는 첫 번째 식은 `#pragma optimize`:

```cpp
#pragma optimize("{opt-list}", on | off)
```

이 pragma를 사용 하면 함수에서 함수 별로 최적화 수준을 설정할 수 있습니다. 이 이상적인 같이 드문 최적화와 함께 지정된 함수 컴파일될 때 응용 프로그램이 충돌 하는 위치입니다. 단일 함수에 대 한 최적화를 해제 하는 데 사용할 수 있습니다.

```cpp
#pragma optimize("", off)
int myFunc() {...}
#pragma optimize("", on)
```

자세한 내용은 참조 [최적화](../../preprocessor/optimize.md)합니다.

인라이닝은 컴파일러를 수행 하 고 여기 몇 가지이 동작을 수정 하는 데 도움이 되는 pragma에 설명 하는 가장 중요 한 최적화 중 하나입니다.

`#pragma inline_recursion` 응용 프로그램 재귀 호출을 인라인 할 수 있는 것인지 여부를 지정 하는 데 유용 합니다. 기본적으로 해제 되어 있습니다. 단순 재귀 작은 함수에 대 한이 서비스 설정 할 수 있습니다. 자세한 내용은 참조 [inline_recursion](../../preprocessor/inline-recursion.md)합니다.

깊이 제한 하는 다른 유용한 pragma 인라인 처리는 `#pragma inline_depth`합니다. 프로그램 또는 함수의의 크기를 제한 하려는 경우에 일반적으로 유용 합니다. 자세한 내용은 참조 [inline_depth](../../preprocessor/inline-depth.md)합니다.

## <a name="restrict-and-assume"></a>__restrict 및 \__assume

성능을 향상 시킬 수 있는 Visual c + + 키워드는 두 가지가: [__restrict](../../cpp/extension-restrict.md) 및 [__assume](../../intrinsics/assume.md)합니다.

용도로 먼저는 `__restrict` 및 `__declspec(restrict)` 서로 구분 합니다. 다소 관련 되어 있는 동안 해당 의미 체계가 서로 다릅니다. `__restrict` 형식 한정자를 같은입니다 `const` 또는 `volatile`, 있지만 포인터 형식에 대 한 단독으로 합니다.

로 한정 되는 포인터 `__restrict` 라고는 *포인터 __restrict*합니다. __Restrict 포인터는만 통해 액세스할 수 있는 포인터는 \_제한 (_r) 포인터입니다. 즉,에서 가리키는 데이터에 액세스 하려면 다른 포인터를 사용할 수 없습니다는 \_제한 (_r) 포인터입니다.

`__restrict` Visual c + + 최적화 프로그램을 위한 강력한 도구로 수는 있지만 매우 주의 하 여 사용 합니다. 잘못 사용 하면 최적화 프로그램 결과로 응용 프로그램이 있는 최적화를 수행할 수 있습니다.

`__restrict` 키워드를 대체는 **/Oa** 이전 버전에서 전환 합니다.

와 `__assume`, 개발자 수 있는 일부 변수의 값에 대 한 가정을 컴파일러를 알 수 있습니다.

예를 들어 `__assume(a < 5);` 변수 코드 줄에는 최적화 프로그램에 알립니다 `a` 5 보다 작은 합니다. 다시 컴파일러 하기 위한 약속입니다. 경우 `a` 실제로 6이 시점에서 프로그램에 다음 컴파일러 최적화 한 후 프로그램의 동작은 예상 되지 않을 수 있습니다. `__assume` switch 문 및 조건 식 전에 가장 유용 합니다.

몇 가지 제한이 있습니다 `__assume`합니다. 먼저 같은 `__restrict`,이만, 이므로 컴파일러에 의해 무시 될 합니다. 또한 `__assume` 현재 구성 된 상수에 대해 변수 부등식만 작동 합니다. 예를 들어 assume(a < b)과 같이 기호로만 구성된 부등식은 사용할 수 없습니다.

## <a name="intrinsic-support"></a>내장 지원

내장 함수는 함수 호출 여기서 컴파일러는 호출에 대 한 기본 지식을 하 고 라이브러리에는 함수를 호출 하는 대신 해당 함수에 대 한 코드를 내보냅니다. 헤더 파일 \<. h > 각각의 지원 되는 하드웨어 플랫폼에 대 한 모든 사용 가능한 내장 함수를 포함 합니다.

내장 함수는 프로그래머는 어셈블리를 사용 하지 않고도 코드 심층적으로 이동 하는 기능을 제공 합니다. 내장 함수를 사용 하 여 다양 한 이점이 있습니다.

- 코드 이식성이 향상 됩니다. 일부 내장 함수에서 사용할 수 있는 여러 CPU 아키텍처입니다.

- 사용자 코드는 가독성을 C/c + +에서 코드를 기록한 여전히 때문입니다.

- 코드는 컴파일러 최적화의 이점은 가져옵니다. 컴파일러 개선 되, 대로 내장 함수에 대 한 코드 생성을 향상 시킵니다.

자세한 내용은 참조 [컴파일러 내장](../../intrinsics/compiler-intrinsics.md)합니다.

## <a name="exceptions"></a>예외

한 성능 예외를 사용 하는 적중 합니다. 특정 최적화를 수행 하는에서 컴파일러를 방해 하는 try 블록을 사용 하는 경우 몇 가지 제한 사항이 제공 됩니다. X86 플랫폼에서 추가 성능 저하는 try 코드 실행 중 생성 해야 하는 추가 상태 정보로 인해 블록입니다. 64 비트 플랫폼에서 실행 블록 만큼, 성능을 저하 시 키 지 않는 하지만 예외가 throw 된 처리기를 찾아서 스택 해제 과정 비용이 수 있습니다.

따라서 다음에 실제로 필요 하지 않은 코드를 try/catch 블록 시 키 지 않도록 하는 것이 좋습니다. 예외를 사용 해야 하는 경우 가능 하면 동기 예외를 사용 합니다. 자세한 내용은 [Structured Exception Handling (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)을 참조하세요.

마지막으로, 예외적인 경우에만 대 한 예외를 throw 합니다. 일반 제어 흐름에 대 한 예외를 사용 하 여 성능이 저하 될 가능성이 생성 됩니다.

## <a name="see-also"></a>참고자료

- [코드 최적화](../../build/reference/optimizing-your-code.md)
