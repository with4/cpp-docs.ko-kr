---
title: "_fcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fcvt_s"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fcvt_s"
  - "_fcvt_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fcvt_s 함수"
  - "부동 소수점 변환, 문자열로"
  - "fcvt_s 함수"
  - "부동 소수점 함수, 숫자를 문자열로 변환"
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _fcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 숫자를 문자열로 변환합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 이 버전은 보안 향상 기능이 포함된 [\_fcvt](../../c-runtime-library/reference/fcvt.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `buffer`  
 변환 결과를 저장하는 제공된 버퍼입니다.  
  
 \[in\] `sizeInBytes`  
 버퍼의 크기\(바이트\)입니다.  
  
 \[in\] `value`  
 변환될 수 있는 숫자  
  
 \[in\] `count`  
 소수점 뒤에 자릿수입니다.  
  
 \[out\] `dec`  
 저장된 소수점 위치에 대한 포인터입니다.  
  
 \[out\] `sign`  
 저장된 부호 표시기에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 0이 됩니다.  오류가 발생한 경우의 반환 값은 오류 코드입니다.  오류 코드는 Errno.h에서 정의 됩니다.  이러한 오류의 목록을 보려면, 다음 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 다음 표에 나열된 것과 같은 잘못된 매개 변수의 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `EINVAL`을 반환합니다.  
  
### 오류 조건  
  
|`buffer`|`sizeInBytes`|값|count|dec|sign|반환|`buffer` 의 값입니다.|  
|--------------|-------------------|-------|-----------|---------|----------|--------|----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|수정 되지 않음|  
|`NULL` 이 아닙니다 \(유효한 메모리 포인트\)|\<\=0|any|any|any|any|`EINVAL`|수정 되지 않음|  
|any|any|any|any|`NULL`|any|`EINVAL`|수정 되지 않음|  
|any|any|any|any|any|`NULL`|`EINVAL`|수정 되지 않음|  
  
 **보안 문제**  
  
 `buffer`가 올바른 메모리를 가리키지 않으며 `NULL`이 아닌 경우, `_fcvt_s`는 액세스 위반을 발생시킬 수 있습니다.  
  
## 설명  
 `_fcvt_s` 함수는 null로 끝나는 문자열을 부동 소수점 숫자로 변환합니다.  `value` 매개 변수는 변환된 부동 소수점 숫자입니다.  `_fcvt_s`은 `value`의 자릿수를 문자열로 저장하고 null 문자 \('\\0'\)를 추가합니다.  `count` 매개 변수는 소숫점 이후에 저장될 자릿수를 지정합니다.  초과 자릿수는 `count`를 반올림합니다.  `count`보다 적은 자릿수의 정밀도인 경우, 문자열은 0으로 채워집니다.  
  
 숫자만이 문자열에 저장됩니다.  소수점의 위치 및 `value`의 부호는 호출 이후 `dec`과 `sign`로부터 얻을 수 있습니다.  `dec` 매개 변수는 정수 값을 가리킵니다. 이 정수 값은 문자열의 시작 부분에 대한 소수점의 위치를 제공합니다.  0 또는 음수 값은 소수점이 첫째 자리의 왼쪽에 위치하는 것을 가리킵니다.  매개 변수 `sign`은 `value`의 부호를 나타내는 정수를 가리킵니다.  이 정수는 `value`가 양수인 경우 0으로 설정되며 `value`가 음수인 경우  0이 아닌 숫자로 설정됩니다.  
  
 `_CVTBUFSIZE` 길이의 버퍼는 부동 소수점 값에 대해 충분해야 합니다.  
  
 `_ecvt_s` 및 `_fcvt_s`에서 `count` 매개 변수의 번역 차이입니다.  `_ecvt_s`는 `count`을 출력 문자열의 전체 자릿수로 해석하며, `_fcvt_s`은 `ount`를 소수점 뒤의 자릿수로 해석합니다.  
  
 C\+\+에서 이 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요가 없습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
## 요구 사항  
  
|Function|필수 헤더|선택적 헤더|  
|--------------|-----------|------------|  
|`_fcvt_s`|\<stdlib.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
 **라이브러리:** 의 모든 버전은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Converted value: 120000**   
## 해당 .NET Framework 항목  
 <xref:System.Convert.ToString%2A>  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)