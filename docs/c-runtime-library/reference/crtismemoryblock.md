---
title: _CrtIsMemoryBlock | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dee3e30e5bde5a3bed67d975c96b00568306f926
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock

지정된 메모리 블록이 로컬 힙 내에 있고 유효한 디버그 힙 블록 형식 식별자를 포함하는지 확인합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>매개 변수

*사용자 데이터*<br/>
확인할 메모리 블록의 시작 부분에 대한 포인터입니다.

*size*<br/>
지정된 블록의 크기(바이트)입니다.

*requestNumber*<br/>
블록의 할당 번호에 대 한 포인터 또는 **NULL**합니다.

*filename*<br/>
블록을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
소스 파일의 줄 번호에 대 한 포인터 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

**_CrtIsMemoryBlock** 반환 **TRUE** 지정 된 메모리 블록은 로컬 힙 내에 있고 유효한 디버그 힙의 블록 형식 식별자가 같지 않으면, 함수 반환 **FALSE**합니다.

## <a name="remarks"></a>설명

**_CrtIsMemoryBlock** 함수 확인 하는 지정 된 메모리 블록은 응용 프로그램의 로컬 힙 내에 올바른 블록 형식 식별자가 있습니다. 또한 이 함수는 메모리 블록 할당이 원래 요청된 경우 개체 할당 순서 번호 및 소스 파일 이름/줄 번호를 가져오는 데도 사용할 수 있습니다. NULL이 아닌 값을 전달는 *requestNumber*, *filename*, 또는 *linenumber* 매개 변수 원인을 **_CrtIsMemoryBlock** 설정 하려면 이러한 매개 변수는 메모리 블록에 있는 값에 로컬 힙에 블록을 찾으면 헤더를 디버깅 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtIsMemoryBlock** 전처리 중 제거 됩니다.

경우 **_CrtIsMemoryBlock** 실패 하면 반환 **FALSE** 출력 매개 변수를 기본값으로 초기화 됩니다: *requestNumber* 및 **lineNumber**  0으로 설정 하 고 *filename* 로 설정 되어 **NULL**합니다.

이 함수는 **TRUE** 또는 **FALSE**를 반환하므로 이를 [_ASSERT](assert-asserte-assert-expr-macros.md) 매크로 중 하나로 전달하여 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다. 다음 예제에서는 지정된 주소가 로컬 힙 내에 없을 경우 어설션 오류가 발생하는 경우를 보여 줍니다.

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

방법에 대 한 자세한 내용은 **_CrtIsMemoryBlock** 다른 디버그 함수 및 매크로 함께 사용할 수 있습니다, 참조 [보고에 대 한 매크로](/visualstudio/debugger/macros-for-reporting)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

[_CrtIsValidHeapPointer](crtisvalidheappointer.md) 항목에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
