---
title: fenv_access | Microsoft Docs
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f74f20b1dcb20c1449d21e91181f8bfb17075b7e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912968"
---
# <a name="fenvaccess"></a>fenv_access

사용 하지 않도록 설정 (**에**) 선택 하거나 선택을 취소 (**오프*) 부동 소수점 환경을 변경할 수 있는 최적화 플래그 테스트 및 모드 변경 합니다.

## <a name="syntax"></a>구문

> **#pragma fenv_access (** { **에** | **오프** } **)**  

## <a name="remarks"></a>설명

기본적으로 **fenv_access** 은 **오프**합니다. 컴파일러가 가정할 수 있습니다 코드에 액세스 하거나 부동 소수점 환경을 조작 하지 않는 경우 여러 부동 소수점 코드 최적화가 수행할 수 있습니다. 설정 **fenv_access** 를 **에** 코드가 액세스 부동 소수점 환경 상태 플래그, 예외를 테스트 하려면 또는 제어 모드 플래그를 설정 하는 컴파일러에 알릴 수 있습니다. 컴파일러는 코드는 부동 소수점 환경을 일관 되 게 액세스할 수 있도록 이러한 최적화를 해제 합니다. 

부동 소수점 동작에 대 한 자세한 내용은 참조 하십시오. [/fp (부동 소수점 동작 지정)](../build/reference/fp-specify-floating-point-behavior.md)합니다.

적용 되는 최적화 종류는 **fenv_access** 됩니다.

- 전역 공통 하위 식 제거

- 코드 이동

- 상수 정리

다른 부동 소수점 pragma는 다음과 같습니다.

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>예제

이 예에서는 설정 **fenv_access** 를 **에** 24 비트 정밀도 부동 소수점 제어 레지스터를 설정 하려면:

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-003
```

주석으로 처리 하는 경우 `#pragma fenv_access (on)` 위의 샘플에서 컴파일러는 컴파일 시간 계산 컨트롤 모드를 사용 하지 않는 때문에 출력은 서로 다른 것을 확인 합니다.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-002
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
