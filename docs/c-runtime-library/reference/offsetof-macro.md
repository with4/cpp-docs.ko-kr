---
title: offsetof 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 308aac2493751cfe2147187ed9848347124a90d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401466"
---
# <a name="offsetof-macro"></a>offsetof 매크로

부모 구조의 시작 부분에서 멤버의 오프셋을 검색합니다.

## <a name="syntax"></a>구문

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>매개 변수

*structName*<br/>
부모 데이터 구조의 이름입니다.

*MemberName*<br/>
부모 데이터 구조에서 오프셋을 결정할 멤버의 이름입니다.

## <a name="return-value"></a>반환 값

**offsetof** 부모 데이터 구조의 시작 부분에서 지정된 된 멤버의 바이트에서 오프셋을 반환 합니다. 이는 비트 필드의 경우 정의되지 않습니다.

## <a name="remarks"></a>설명

**offsetof** 매크로의 바이트 오프셋을 반환 *memberName* 지정 된 구조의 시작 부분부터 *structName* 형식의 값으로 **size_ t**합니다. 형식을 지정할 수는 **구조체** 키워드입니다.

> [!NOTE]
> **offsetof** 함수가 아니며 C 프로토타입을 사용 하 여 설명할 수 없습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
