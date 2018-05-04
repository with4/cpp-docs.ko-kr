---
title: _countof 매크로 | Microsoft 문서
ms.custom: ''
ms.date: 03/22/2018
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
- _countof
- countof
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f30df64b045e2af6181d343a4eafb962d22eaa05
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="countof-macro"></a>_countof 매크로

정적으로 할당 한 배열의 요소 수를 계산합니다.

## <a name="syntax"></a>구문

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>매개 변수

*array*<br/>
배열 이름입니다.

## <a name="return-value"></a>반환 값

으로 표시 되는 배열에 있는 요소의 수는 **size_t**합니다.

## <a name="remarks"></a>설명

**_countof** 함수 형식 전처리기 매크로로 구현 됩니다. C + + 버전에 대 한 포인터는 정적으로 선언 된 배열 대신 전달 되는 경우 컴파일 타임에 감지 하는 추가 템플릿 기계 있습니다.

되도록 *배열* 은 실제 배열, 포인터가 아닙니다. C에서는 **_countof** 경우 잘못 된 결과가 생성 *배열* 대 한 포인터입니다. C + +에서는 **_countof** 경우 컴파일을 *배열* 대 한 포인터입니다.  배열 함수에 매개 변수로 전달 *포인터에 decays*는 함수 내에서 사용할 수 없음을 의미 하는 **_countof** 배열의 범위를 확인 합니다.

## <a name="requirements"></a>요구 사항

|매크로|필수 헤더|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

## <a name="example"></a>예제

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>참고자료

[sizeof 연산자](../../cpp/sizeof-operator.md)<br/>
