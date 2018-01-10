---
title: "_countof 매크로 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd7273690f75daf4d011a18da354ab8359268556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="countof-macro"></a>_countof 매크로
정적으로 할당된 배열의 요소 수를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `array`  
 배열 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 배열의 요소 수이며 `size_t`로 표현됩니다.  
  
## <a name="remarks"></a>설명  
 `array`는 실제로 포인터가 아니라 배열입니다. C에서 `_countof`가 포인터일 경우 `array`는 잘못된 결과를 생성합니다. C++에서 `_countof`가 포인터일 경우 `array`는 컴파일에 실패합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|매크로|필수 헤더|  
|-----------|---------------------|  
|`_countof`|\<stdlib.h>|  
  
## <a name="example"></a>예  
  
```  
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
  
## <a name="see-also"></a>참고 항목  
 [sizeof 연산자](../../cpp/sizeof-operator.md)