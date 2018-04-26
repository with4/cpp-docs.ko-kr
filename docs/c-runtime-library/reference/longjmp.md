---
title: longjmp | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- longjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a593c2dcdfe1731ee5c6438c7a330e7f4ea8740
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="longjmp"></a>longjmp

스택 환경 및 실행 로캘을 복원합니다.

## <a name="syntax"></a>구문

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>매개 변수

*env* 환경을 저장 된 변수입니다.

*값* 반환 될 값을 **setjmp** 호출 합니다.

## <a name="remarks"></a>설명

**longjmp** 함수에서 이전에 저장 된 스택 환경 및 실행 로캘을 복원 *env* 여 **setjmp**합니다. **setjmp** 및 **longjmp** 는 로캘이 아닌을 실행 하는 방법을 제공 **goto**; 실행 제어 하지 않고 전에 호출된 된 루틴에서 오류 처리 또는 복구 코드를 전달 하려면 일반적으로 사용 됩니다 일반을 사용 하 여 호출 하 고 규칙을 반환 합니다.

에 대 한 호출 **setjmp** 현재 스택 환경에 저장 되도록 *env*합니다. 후속 호출에 **longjmp** 저장된 된 환경을 복원 되 고 해당 바로 다음 지점의 제어 돌아갑니다 **setjmp** 호출 합니다. 실행이 다시 시작 처럼 *값* 반환한 것에 **setjmp** 호출 합니다. 될 때가지고 있던 값을 포함 하는 컨트롤을 받는 루틴에 액세스할 수 있는 모든 변수 (레지스터 변수 제외)의 값 **longjmp** 호출 되었습니다. 레지스터 변수 값은 예측할 수 없습니다. 반환한 값 **setjmp** 0이 아니어야 합니다. *value*가 0으로 전달되는 경우 값 1은 실제 반환에서 대체됩니다.

호출 **longjmp** 함수를 호출 하기 전에 **setjmp** 반환 하 고; 그렇지 않으면 결과 예측할 수 없습니다.

사용 하는 경우 다음과 같은 제한 사항이 관찰 **longjmp**:

- 레지스터 변수 값이 그대로 유지된다고 가정하지 마십시오. 호출 하는 루틴의 레지스터 변수 값 **setjmp** 이후 적절 한 값을 복원할 수 있습니다 **longjmp** 실행 됩니다.

- 사용 하지 마십시오 **longjmp** 부동 소수점 예외로 인해 인터럽트가 발생 하지 않는 한 인터럽트 처리 루틴 외부로 제어를 전송 하도록 합니다. 프로그램을 통해 인터럽트 처리기에서 반환할 수 있습니다이 경우 **longjmp** 것 먼저 다시 초기화 부동 소수점 연산 패키지를 호출 하 여 **_fpreset**합니다.

     **참고** 사용할 때는 주의 해야 **setjmp** 및 **longjmp** c + + 프로그램에서 합니다. 이러한 함수는 C++ 개체 의미 체계를 지원하지 않기 때문에 C++ 예외 처리 메커니즘을 사용하는 것이 보다 안전합니다.

자세한 내용은 [setjmp 및 longjmp 사용](../../cpp/using-setjmp-longjmp.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

[_fpreset](fpreset.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)<br/>
