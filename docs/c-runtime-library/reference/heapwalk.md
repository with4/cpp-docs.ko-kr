---
title: _heapwalk | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d98260ce281bc8773f597dae5897afe4beee0bc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="heapwalk"></a>_heapwalk

힙을 이동하고 다음 항목에 대한 정보를 반환합니다.

> [!IMPORTANT]
> 이 API는 디버그 빌드를 제외하고 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>매개 변수

*entryinfo*<br/>
힙 정보를 포함할 버퍼입니다.

## <a name="return-value"></a>반환 값

**_heapwalk** Malloc.h에 정의 된 다음 정수 매니페스트 상수 중 하나를 반환 합니다.

|반환 값|의미|
|-|-|
|**_HEAPBADBEGIN**| 초기 헤더 정보가 잘못되었거나 없습니다.|
|**_HEAPBADNODE**| 힙이 손상되었거나 잘못된 노드가 있습니다.|
|**_HEAPBADPTR**| **_heapinfo** 필드는 **_HEAPINFO** 구조 힙에 대 한 유효한 포인터를 포함 하지 않습니다 또는 *entryinfo* 가 null 포인터입니다.|
|**_HEAPEND**| 힙 끝에 성공적으로 도달했습니다.|
|**_HEAPEMPTY**| 힙이 초기화되지 않았습니다.|
|**_HEAPOK**| 지금;까지 오류가 없습니다 *entryinfo* 다음 힙 항목에 대 한 정보로 업데이트 됩니다.|

또한 오류가 발생 하는 경우 **_heapwalk** 설정 **errno** 를 **ENOSYS**합니다.

## <a name="remarks"></a>설명

**_heapwalk** 함수를 사용 하면 프로그램의 힙 관련 문제를 디버깅 합니다. 함수 호출을 하는 각 항목을 트래버스하는 힙에 안내 하 고 형식의 구조에 대 한 포인터를 반환 **_HEAPINFO** 다음 힙 항목에 대 한 정보가 들어 있는입니다. **_HEAPINFO** , Malloc.h에 정의 된 형식에는 다음과 같은 요소가 있습니다.

|필드|의미|
|-|-|
|`int *_pentry`|힙 항목 포인터.|
|`size_t _size`|힙 항목의 크기.|
|`int _useflag`|힙 항목이 사용 중인지 여부를 나타내는 플래그.|

에 대 한 호출 **_heapwalk** 반환 하는 **_HEAPOK** 에 있는 항목의 크기를 저장는 **_size** 필드 및 집합은 **_heapinfo** 필드 중 하나를 **_FREEENTRY** 또는 **_USEDENTRY** (둘 다는 Malloc.h에 정의 된 상수). 힙에 있는 첫 번째 항목에 대 한이 정보를 얻으려면 전달 **_heapwalk** 에 대 한 포인터는 **_HEAPINFO** 갖는 **_heapinfo** 멤버는 **NULL** . 운영 체제를 지원 하지 않는 경우 **_heapwalk**함수 반환 (예: Windows 98) **_HEAPEND** 설정 **errno** 를 **ENOSYS**.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *entryinfo* 가 null 포인터에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수가 반환 하 고 **_HEAPBADPTR**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_heapwalk.c

// This program "walks" the heap, starting
// at the beginning (_pentry = NULL). It prints out each
// heap entry's use, location, and size. It also prints
// out information about the overall state of the heap as
// soon as _heapwalk returns a value other than _HEAPOK
// or if the loop has iterated 100 times.

#include <stdio.h>
#include <malloc.h>

void heapdump(void);

int main(void)
{
    char *buffer;

    heapdump();
    if((buffer = (char *)malloc(59)) != NULL)
    {
        heapdump();
        free(buffer);
    }
    heapdump();
}

void heapdump(void)
{
    _HEAPINFO hinfo;
    int heapstatus;
    int numLoops;
    hinfo._pentry = NULL;
    numLoops = 0;
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&
          numLoops < 100)
    {
        printf("%8s block at %Fp of size %4.4X\n",
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),
               hinfo._pentry, hinfo._size);
        numLoops++;
    }

    switch(heapstatus)
    {
    case _HEAPEMPTY:
        printf("OK - empty heap\n");
        break;
    case _HEAPEND:
        printf("OK - end of heap\n");
        break;
    case _HEAPBADPTR:
        printf("ERROR - bad pointer to heap\n");
        break;
    case _HEAPBADBEGIN:
        printf("ERROR - bad start of heap\n");
        break;
    case _HEAPBADNODE:
        printf("ERROR - bad node in heap\n");
        break;
    }
}
```

```Output
    USED block at 00310650 of size 0100
    USED block at 00310758 of size 0800
    USED block at 00310F60 of size 0080
    FREE block at 00310FF0 of size 0398
    USED block at 00311390 of size 000D
    USED block at 003113A8 of size 00B4
    USED block at 00311468 of size 0034
    USED block at 003114A8 of size 0039
...
    USED block at 00312228 of size 0010
    USED block at 00312240 of size 1000
    FREE block at 00313250 of size 1DB0
OK - end of heap
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
