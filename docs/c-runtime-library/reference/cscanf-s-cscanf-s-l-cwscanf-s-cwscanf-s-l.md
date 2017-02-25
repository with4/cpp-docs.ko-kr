---
title: "_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwscanf_s_l"
  - "_cwscanf_s"
  - "_cscanf_s"
  - "_cscanf_s_l"
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
  - "cscanf_s"
  - "cscanf_s_l"
  - "cwscanf_s"
  - "_cwscanf_s"
  - "_tcscanf_s"
  - "_cscanf_s"
  - "_cwscanf_s_l"
  - "_cscanf_s_l"
  - "cwscanf_s_l"
  - "_tcscanf_s_l"
  - "tcscanf_s"
  - "tcscanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cscanf_s 함수"
  - "_cscanf_s_l 함수"
  - "_cwscanf_s 함수"
  - "_cwscanf_s_l 함수"
  - "_tcscanf_s 함수"
  - "_tcscanf_s_l 함수"
  - "콘솔[C++], 읽기"
  - "cscanf_s 함수"
  - "cscanf_s_l 함수"
  - "cwscanf_s 함수"
  - "cwscanf_s_l 함수"
  - "데이터[C++], 콘솔에서 읽기"
  - "데이터 읽기[C++], 콘솔에서"
  - "tcscanf_s 함수"
  - "tcscanf_s_l 함수"
ms.assetid: 9ccab74d-916f-42a6-93d8-920525efdf4b
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

읽기 콘솔에서 데이터를 포맷합니다.  이러한 더 보안 버전의 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md) 에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _cscanf_s(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_s_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf_s(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_s_l(   
   const wchar_t *format,  
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
 성공적으로 변환되어 할당된 필드 개수입니다.  반환 값을 읽지만 할당되지 않은 필드를 포함하지 않습니다.  반환 값은 파일의 끝에 읽기 위해 시도하는 `EOF` 입니다.  이 운영 체제의 명령줄 수준에서 키보드 입력을 리디렉션할 때 발생할 수 있습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 의미합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  만약 `format` 이 NULL 포인터인 경우, 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF` 를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## 설명  
 이 `_cscanf_s` 함수는 `argument` 으로 주는 지정된 위치의 콘솔에서 데이터를 바로 읽습니다.  이 [\_getche](../../c-runtime-library/reference/getch-getwch.md) 함수는 문자를 읽는데 사용합니다.  임의의 각 매개변수는 `format`에서 형식 지정자와 일치하는 특정 형식의 변수에 대한 포인터가 되어야 합니다.  형식은 입력 필드의 해석을 제어하고 [scanf\_s](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 함수의 `format` 인수와 동일한 폼과 함수를 가집니다.  이 `_cscanf_s` 가 정상적으로 입력된 문자를 반영하는 동안, `_ungetch` 의 마지막 호출에 하지 않게 됩니다.  
  
 이`scanf` 제품군의 함수들의 다른 보안 버전같이,`_cscanf_s` 과 `_cswscanf_s` 는 `c`, `C`, `s`, `S`, `[` 형식 필드 문자를 위한 크기 인수를 요구합니다.  자세한 내용은 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)을 참조하십시오.  
  
> [!NOTE]
>  이 크기 매개 변수는 `size_t`이 아닌 `unsigned` 형식입니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcscanf_s`|`_cscanf_s`|`_cscanf_s`|`_cwscanf_s`|  
|`_tcscanf_s_l`|`_cscanf_s_l`|`_cscanf_s_l`|`_cwscanf_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_cscanf_s`,`_cscanf_s_l`|\<conio.h\>|  
|`_cwscanf_s`, `_cwscanf_s_l`|\<conio.h\> 또는 \<wchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_cscanf_s.c  
// compile with: /c  
/* This program prompts for a string  
 * and uses _cscanf_s to read in the response.  
 * Then _cscanf_s returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int result, n[3];  
   int i;  
  
   result = _cscanf_s( "%i %i %i", &n[0], &n[1], &n[2] );  
   _cprintf_s( "\r\nYou entered " );  
   for( i=0; i<result; i++ )  
      _cprintf_s( "%i ", n[i] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## 입력  
  
```  
1 2 3  
```  
  
## Output  
  
```  
You entered 1 2 3  
```  
  
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)