---
title: "getc, getwc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getwc
- getc
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
- _gettc
- getwc
- _gettchar
- getc
dev_langs: C++
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 78a94d954631dfffbdcdc4bcad252599c673f44b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="getc-getwc"></a>getc, getwc
스트림에서 문자를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 입력 스트림입니다.  
  
## <a name="return-value"></a>반환 값  
 읽은 문자를 반환합니다. 읽기 오류 또는 파일 끝 조건을 표시하기 위해 `getc`는 `EOF`를 반환하고 `getwc`는 `WEOF`를 반환합니다. `getc`의 경우 `ferror` 또는 `feof`를 사용하여 오류 또는 파일 끝이 있는지 확인합니다. `stream`이 `NULL`인 경우 `getc` 및 `getwc`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속 허용 된 경우 이러한 함수가 반환 `EOF` (또는 `WEOF` 에 대 한 `getwc`) 설정 하 고 `errno` 를 `EINVAL`합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 각 루틴은 파일에서 현재 위치의 단일 문자를 읽고 다음 문자를 가리킬 연결된 파일 포인터(정의된 경우)를 늘립니다. 파일은 `stream`과 연결됩니다.  
  
 이러한 함수는 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 [_getc_nolock, _getwc_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md)을 참조하세요.  
  
 이어서 루틴별 설명이 제공됩니다.  
  
|루틴|설명|  
|-------------|-------------|  
|`getc`|`fgetc`와 같지만 함수 및 매크로로 구현됩니다.|  
|`getwc`|와이드 문자 버전의 `getc`입니다. `stream`이 텍스트 모드 또는 이진 모드로 열리는지에 따라 멀티바이트 문자 또는 와이드 문자를 읽습니다.|  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`getc`|\<stdio.h>|  
|`getwc`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## <a name="input-crtgetctxt"></a>입력: crt_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>출력  
  
```  
Input was: Line one.  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)