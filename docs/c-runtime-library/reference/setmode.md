---
title: _setmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setmode
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
- _setmode
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: f6d84d5f40b49edaf4e79059a6661a51ca6c209a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="setmode"></a>_setmode
파일 변환 모드를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _setmode (  
   int fd,  
   int mode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 파일 설명자입니다.  
  
 `mode`  
 새 변환 모드입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 이전 변환 모드를 반환합니다.  
  
 함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 이 함수는-1 반환 하 고 집합을 계속 하려면 실행 허용 된 경우 `errno` 을 `EBADF`, 된 잘못 된 파일 설명자를 나타내는 또는 `EINVAL`, 잘못 된 나타냅니다 `mode` 인수입니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## <a name="remarks"></a>설명  
 `_setmode` 함수는 `mode`에서 제공하는 파일 변환 모드인 `fd`로 설정됩니다. `_O_TEXT`를 `mode`로 전달하면 텍스트(즉, 변환된) 모드가 설정됩니다. 캐리지 리턴-줄 바꿈된 (CR-LF) 조합은 단일 줄 바꿈 문자 입력 시로 변환 됩니다. 줄 바꿈 문자는 출력 시 CR-LF 조합으로 변환됩니다. `_O_BINARY`를 전달하면 이러한 변환이 억제되는 이진(변환되지 않은) 모드가 설정됩니다.  
  
 전달할 수도 있습니다 `_O_U16TEXT`, `_O_U8TEXT`, 또는 `_O_WTEXT` 이 문서의 뒷부분에서 두 번째 예제와 같이 유니코드 모드를 사용할 수 있도록 합니다. `_setmode`는 일반적으로 `stdin` 및 `stdout`의 기본 변환 모드를 수정하는 데 사용되지만 아무 파일에나 사용할 수 있습니다. `_setmode`를 스트림의 파일 설명자에 적용한 경우 스트림에 대한 입력 또는 출력 작업을 수행하기 전에 `_setmode`를 호출합니다.  
  
> [!CAUTION]
>  파일 스트림에 데이터를 쓰는 경우 `_setmode`를 사용하여 모드를 변경하기 전에 [fflush](../../c-runtime-library/reference/fflush.md)를 사용하여 코드를 명시적으로 플러시합니다. 코드를 플러시하지 않은 경우 예기치 않은 동작이 발생할 수 있습니다. 스트림에 데이터를 쓰지 않을 경우 코드를 플러시할 필요가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|----------------------|  
|`_setmode`|\<io.h>|\<fcntl.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
```Output  
'stdin' successfully changed to binary mode  
```  
  
## <a name="example"></a>예제  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)
