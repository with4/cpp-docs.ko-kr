---
title: "_getc_nolock, _getwc_nolock | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getc_nolock
- _getwc_nolock
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
- getc_nolock
- _gettc_nolock
- _getc_nolock
- getwc_nolock
- gettc_nolock
- _getwc_nolock
dev_langs:
- C++
helpviewer_keywords:
- characters, reading
- _getc_nolock function
- _getwc_nolock function
- getwc_nolock function
- streams, reading characters from
- reading characters from streams
- getc_nolock function
- gettc_nolock function
- _gettc_nolock function
ms.assetid: eb37b272-e177-41c9-b077-12ce7ffd3b88
caps.latest.revision: 16
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 89144f6750dcb7b264f9783b2454826be45e036c
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="getcnolock-getwcnolock"></a>_getc_nolock, _getwc_nolock
스트림에서 문자를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _getc_nolock(   
   FILE *stream   
);  
wint_t _getwc_nolock(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 입력 스트림입니다.  
  
## <a name="return-value"></a>반환 값  
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 이러한 함수는 호출 스레드를 잠그지 않는다는 점을 제외하고 `getc` 및 `getwc`와 동일합니다. 이들은 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_gettc_nolock`|`getc_nolock`|`getc_nolock`|`getwc_nolock`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`getc_nolock`|\<stdio.h>|  
|`getwc_nolock`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_getc_nolock.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc_nolock.txt".  
    fopen_s(&fp, "crt_getc_nolock.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc_nolock.txt.\n");  
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
  
## <a name="input-crtgetcnolocktxt"></a>입력: crt_getc_nolock.txt  
  
```  
Line the first.  
Line the second.  
```  
  
### <a name="output"></a>출력  
  
```  
Input was: Line the first.  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)
