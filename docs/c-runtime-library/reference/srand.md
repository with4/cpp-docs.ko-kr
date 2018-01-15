---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: srand
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
f1_keywords: srand
dev_langs: C++
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
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 205dcb2ba7d61dff1286fd926e3f10cf2a162e9a
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="srand"></a>srand

사용 하는 의사 난수 생성기에 대 한 시작 시드 값을 설정 하는 `rand` 함수입니다.

## <a name="syntax"></a>구문

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>매개 변수

*시드*  
의사 난수 생성을 위한 시드

## <a name="remarks"></a>설명

`srand` 함수는 현재 스레드에서 일련의 의사 난수 정수 생성을 위한 시작점을 설정합니다. 호출 결과의 동일한 시퀀스를 만드는 생성자를 다시 초기화 하려면는 `srand` 함수를 사용 하 여 동일한 *시드* 다시 인수입니다. 다른 모든 값에 대 한 *시드* 생성기 의사 난수 시퀀스에서 서로 다른 시작 지점으로 설정 합니다. `rand`는 생성된 의사 난수를 검색합니다. 호출 `rand` 를 호출 하기 전에 `srand` 호출할 때와 동일한 시퀀스를 생성 `srand` 와 *시드* 1로 전달 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`srand`|\<stdlib.h>|

호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.

## <a name="example"></a>예

[rand](../../c-runtime-library/reference/rand.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
