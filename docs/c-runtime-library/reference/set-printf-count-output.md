---
title: _set_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_printf_count_output
- _set_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 8229146184b4d4d0cfbccd60f6c4209356db5f8f
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="setprintfcountoutput"></a>_set_printf_count_output
[printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 패밀리 함수가 `%n` 형식을 지원하거나 지원하지 않도록 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `enable`  
 0이 아닌 값은 `%n` 지원을 사용하도록 설정하고, 0은 `%n` 지원을 사용하지 않도록 설정합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 이 함수를 호출하기 전의 `%n` 지원 상태입니다. `%n` 지원이 사용되면 0이 아닌 값이고, 해당 지원이 사용되지 않으면 0입니다.  
  
## <a name="remarks"></a>설명  
 보안상의 이유로 `%n` 형식 지정자에 대한 지원은 기본적으로 `printf` 및 모든 해당 변형 항목에서 사용되지 않습니다. `%n`이 `printf` 형식 사양에서 발견되는 경우 기본 동작은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출하는 것입니다. 호출 `_set_printf_count_output` 0이 아닌 인수를 사용 하면 `printf`-해석 패밀리 함수 `%n` 에 설명 된 대로 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_set_printf_count_output`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```C  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
```Output  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## <a name="see-also"></a>참고 항목  
 [_get_printf_count_output](../../c-runtime-library/reference/get-printf-count-output.md)
