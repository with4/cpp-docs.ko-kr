---
title: "_snscanf, _snscanf_l, _snwscanf, _snwscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwscanf"
  - "_snscanf_l"
  - "_snscanf"
  - "_snwscanf_l"
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
  - "_snscanf"
  - "_snscanf_l"
  - "_snwscanf"
  - "snscanf_l"
  - "snscanf"
  - "_sntscanf_l"
  - "_sntscanf"
  - "_snwscanf_l"
  - "sntscanf_l"
  - "sntscanf"
  - "snwscanf"
  - "snwscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_snscanf 함수"
  - "_snscanf_l 함수"
  - "_sntscanf 함수"
  - "_sntscanf_l 함수"
  - "_snwscanf 함수"
  - "_snwscanf_l 함수"
  - "데이터 읽기, 문자열"
  - "snscanf 함수"
  - "snscanf_l 함수"
  - "sntscanf 함수"
  - "sntscanf_l 함수"
  - "snwscanf 함수"
  - "snwscanf_l 함수"
  - "문자열[C++], 읽기"
  - "문자열[C++], 데이터 읽기"
ms.assetid: da1ac890-f905-4cd7-954b-3c90957b5551
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _snscanf, _snscanf_l, _snwscanf, _snwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에서 지정된 길이의 서식이 지정된 데이터를 읽습니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_snscanf\_s, \_snscanf\_s\_l, \_snwscanf\_s, \_snwscanf\_s\_l](../../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
int __cdecl _snscanf(  
   const char * input,  
   size_t length,  
   const char * format,  
   ...  
);  
int __cdecl _snscanf_l(  
   const char * input,  
   size_t length,  
   const char * format,  
   locale_t locale,  
   ...  
);  
int __cdecl _snwscanf(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   ...  
);  
int __cdecl _snwscanf_l(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   locale_t locale,  
   ...  
);  
```  
  
#### 매개 변수  
 `input`  
 검사할 입력 문자열입니다.  
  
 `length`  
 검사할 `input`의 문자 수입니다.  
  
 `format`  
 하나 이상의 형식 지정자입니다.  
  
 `... (optional)`  
 `format`의 형식 지정에 의해 입력 문자열로부터 추출된 값을 저장하는 데에 사용되는 변수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 해당 함수는 모두 성공적으로 변환, 배정된 필드 수를 반환합니다. 이때 읽기는 되었지만 지정되지 않은 필드는 반환 값에 포함되지 않습니다.  반환 값 0은 어떤 필드도 할당되지 않았음을 나타냅니다.  오류가 발생하거나 첫 번째 변환 전에 문자열의 끝에 도달할 경우 반환 값은 `EOF`입니다.  자세한 내용은, [sscanf](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)을 참고하세요.  
  
 만일 `input` 또는 `format` 가 `NULL` 포인터이거나 `length` 가 0보다 적거나 같은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EOF`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이 함수는 `sscanf`와 비슷하지만 입력된 문자열로부터 검사하기 위한 고정된 숫자의 문자를 지정하는 기능을 제공한다는 점이 다릅니다.  자세한 내용은, [sscanf](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)을 참고하세요.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_sntscanf`|`_snscanf`|`_snscanf`|`_snwscanf`|  
|`_sntscanf_l`|`_snscanf_l`|`_snscanf_l`|`_snwscanf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_snscanf`, `_snscanf_l`|\<stdio.h\>|  
|`_snwscanf`, `_snwscanf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_snscanf.c  
// compile with: /W3  
  
#include <stdio.h>  
int main( )  
{  
   char  str1[] = "15 12 14...";  
   wchar_t  str2[] = L"15 12 14...";  
   char  s1[3];  
   wchar_t  s2[3];  
   int   i;  
   float fp;  
  
   i = _snscanf( str1, 6,  "%s %f", s1, &fp); // C4996  
   // Note: _snscanf is deprecated; consider using _snscanf_s instead  
   printf("_snscanf converted %d fields: ", i);  
   printf("%s and %f\n", s1, fp);  
  
   i = _snwscanf( str2, 6,  L"%s %f", s2, &fp); // C4996  
   // Note: _snwscanf is deprecated; consider using _snwscanf_s instead  
   wprintf(L"_snwscanf converted %d fields: ", i);  
   wprintf(L"%s and %f\n", s2, fp);  
}  
```  
  
  **\_snscanf converted 2 fields: 15 and 12.000000**  
**\_snwscanf converted 2 fields: 15 and 12.000000**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)