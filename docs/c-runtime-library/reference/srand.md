---
title: srand | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- srand
dev_langs:
- C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2b527561e312ce9c50dce106a243d7e49a1d303
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406890"
---
# <a name="srand"></a>srand

사용 하는 의사 난수 생성기에 대 한 시작 시드 값을 설정 하는 **rand** 함수입니다.

## <a name="syntax"></a>구문

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>매개 변수

*시드* 의사 난수 생성에 대 한 초기값

## <a name="remarks"></a>설명

**srand** 함수는 현재 스레드의 의사 난수 정수 계열을 생성 하기 위한 시작 지점을 설정 합니다. 호출 결과의 동일한 시퀀스를 만드는 생성자를 다시 초기화 하려면는 **srand** 함수를 사용 하 여 동일한 *시드* 다시 인수입니다. 다른 모든 값에 대 한 *시드* 생성기 의사 난수 시퀀스에서 서로 다른 시작 지점으로 설정 합니다. **rand** 생성 되는 난수를 검색 합니다. 호출 **rand** 를 호출 하기 전에 **srand** 호출할 때와 동일한 시퀀스를 생성 **srand** 와 *시드* 1로 전달 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[rand](rand.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
