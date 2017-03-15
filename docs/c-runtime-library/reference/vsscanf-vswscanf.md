---
title: "vsscanf, vswscanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vsscanf"
  - "vswscanf"
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
  - "_vstscanf"
  - "vsscanf"
  - "vswscanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vsscanf 함수"
  - "vswscanf 함수"
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# vsscanf, vswscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에서 형식 데이터를 읽습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [vsscanf\_s, vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)를 참조하십시오.  
  
## 구문  
  
```  
int vsscanf(  
   const char *buffer,  
   const char *format,  
   va_list arglist  
);  
int vswscanf(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   va_list arglist  
);  
```  
  
#### 매개 변수  
 `buffer`  
 저장된 데이터  
  
 `format`  
 형식 컨트롤 문자열입니다.  자세한 내용은 [형식 사양 필드: scanf 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)을 참조하십시오.  
  
 `arglist`  
 가변 길이 인수 목록.  
  
## 반환 값  
 해당 함수는 각각 성공적으로 변환, 배정된 필드 수를 반환합니다. 이때 읽기는 되었지만 지정되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  오류가 발생하거나 첫 번째 변환 전에 문자열의 끝에 도달할 경우 반환 값은 `EOF`입니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 `buffer` 또는 `format`이 `NULL` 포인터인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `vsscanf` 함수는 `buffer`에서 `arglist` 인수 목록의 각 인수에 지정된 위치로 데이터를 읽습니다.  목록의 모든 인수는 특정 형식을 가진 변수에 대한 포인터가 되며 그 형식은 `format`의 유형 지정자에 해당됩니다.  `format` 인수는 입력 필드의 해석을 제어하고 `scanf` 함수의 `format` 인수와 동일한 폼과 함수를 가집니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `vsscanf`를 사용하여 문자열을 읽을 경우 `%s` 서식의 너비\(예: `"%s"` 대신 `"%32s"`\)를 항상 지정해야 합니다. 그렇지 않으면 서식이 잘못 지정된 입력으로 버퍼 오버런이 발생할 수 있습니다.  
  
 `vswscanf`는 `vsscanf`의 와이드 문자 버전이며, `vswscanf`에 대한 인수는 와이드 문자 문자열입니다.  `vsscanf`는 멀티 바이트 16진수 문자를 처리하지 않습니다.  `vswscanf`는 유니코드 전자 16 진수 또는 "호환성 영역" 문자를 처리하지 않습니다.  그렇지 않으면 `vswscanf`과 `vsscanf`은 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vstscanf`|`vsscanf`|`vsscanf`|`vswscanf`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`vsscanf`|\<stdio.h\>|  
|`vswscanf`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_vsscanf.c  
// compile with: /W3  
// This program uses vsscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vsscanf(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf(tokenstring, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    char  tokenstring[] = "15 12 14...";  
    char  s[81];  
    char  c;  
    int   i;  
    float fp;  
  
    // Input various data from tokenstring:  
    // max 80 character string:  
    call_vsscanf(tokenstring, "%80s", s);  
    call_vsscanf(tokenstring, "%c", &c);  
    call_vsscanf(tokenstring, "%d", &i);  
    call_vsscanf(tokenstring, "%f", &fp);  
  
    // Output the data read  
    printf("String    = %s\n", s);  
    printf("Character = %c\n", c);  
    printf("Integer:  = %d\n", i);  
    printf("Real:     = %f\n", fp);  
}  
```  
  
  **문자열    \= 15**  
**문자 \= 1**  
**정수: \= 15**  
**실수:     \= 15.000000**   
## 해당 .NET Framework 항목  
 `Parse` 메서드\(예: [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)\)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf\_s, vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)