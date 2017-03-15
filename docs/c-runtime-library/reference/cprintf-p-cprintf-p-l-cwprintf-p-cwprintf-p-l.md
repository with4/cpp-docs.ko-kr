---
title: "_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cprintf_p_l"
  - "_cwprintf_p_l"
  - "_cwprintf_p"
  - "_cprintf_p"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cprintf_p"
  - "cwprintf_p"
  - "tcprintf_p"
  - "_cwprintf_p_l"
  - "_cprintf_p"
  - "csprintf_p_l"
  - "_cprintf_p_l"
  - "_cwprintf_p"
  - "_tcprintf_p"
  - "cprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cprintf_p 함수"
  - "_cprintf_p_l 함수"
  - "_cwprintf_p 함수"
  - "_cwprintf_p_l 함수"
  - "_tcprintf_p 함수"
  - "_tcprintf_p_l 함수"
  - "cprintf_p 함수"
  - "cprintf_p_l 함수"
  - "cwprintf_p 함수"
  - "cwprintf_p_l 함수"
  - "tcprintf_p 함수"
  - "tcprintf_p_l 함수"
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 문자열에서 형식을 지정하고 콘솔에 인쇄하고 위치 매개 변수를 지원합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
int _cprintf_p(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_p_l(   
   const char * format,  
   locale_t locale [,   
   argument] ...   
);  
int _cwprintf_p(  
   const wchar * format [,   
   argument] ...  
);  
int _cwprintf_p_l(  
   const wchar * format,  
   locale_t locale [,  
   argument] ...  
);  
```  
  
#### 매개 변수  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument`  
 선택적 매개 변수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 인쇄된 문자 수 또는 오류가 발생하는 경우 음수 값입니다.  
  
## 설명  
 이러한 함수는 문자를 출력하는 `_putch` 및 `_putwch` 함수를 사용하여 일련의 문자 및 값의 형식을 지정하고 콘솔에 직접 인쇄합니다.  각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다.  이 형식은 `format`printf 함수에 대한 [매개 변수와 동일한 폼과 기능을 가집니다.](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) `_cprintf_p`와 `cprintf_s`의 차이점은 `_cprintf_p`에서 위치 매개 변수를 지원한다는 점입니다. 이는 인수가 형식 문자열에서 사용되는 순서를 지정할 수 있습니다.  자세한 내용은 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.  
  
 `fprintf_p`, `printf_p` 및 `sprintf_p` 함수와 달리 `_cprintf_p` 또는 `_cwprintf_p`는 출력할 때 줄 바꿈 문자를 캐리지 리턴 줄 바꿈\(CR\-LF\) 조합으로 변환하지 않습니다.  중요한 차이점은 `_cwprintf_p`가 Windows NT에서 사용될 때 유니코드 문자를 표시한다는 점입니다.  `_cprintf_p`와 달리 `_cwprintf_p`는 현재 콘솔 로캘 설정을 사용합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하세요.  
  
 또한 `_cprintf_s` 및 `_cwprintf_s`와 같이 입력 포인터 및 형식 문자열의 유효성을 검사합니다.  `format` 또는 `argument`가 `NULL`이거나 형식 문자열에 잘못된 형식 지정 문자가 포함되어 있는 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우 이러한 함수가 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcprintf_p`|`_cprintf_p`|`_cprintf_p`|`_cwprintf_p`|  
|`_tcprintf_p_l`|`_cprintf_p_l`|`_cprintf_p_l`|`_cwprintf_p_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_cprintf_p`,`_cprintf_p_l`|\<conio.h\>|  
|`_cwprintf_p`,`_cwprintf_p_l`|\<conio.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_cprintf_p.c  
// This program displays some variables to the console  
// using the _cprintf_p function.  
  
#include <conio.h>  
  
int main( void )  
{  
    int         i = -16,  
                h = 29;  
    unsigned    u = 62511;  
    char        c = 'A';  
    char        s[] = "Test";  
  
    // Note that console output does not translate  
    // \n as standard output does. Use \r\n instead.  
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",   
                h, i, u, c, s );  
}  
```  
  
  **\-16  001d  62511  A Test**   
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)   
 [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)