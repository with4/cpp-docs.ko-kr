---
title: "_gcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt_s"
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
  - "_gcvt_s"
  - "gcvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt_s 함수"
  - "변환, 부동 소수점을 문자열로"
  - "CVTBUFSIZE"
  - "부동 소수점 함수, 숫자를 문자열로 변환"
  - "gcvt_s 함수"
  - "숫자, 문자열로 변환"
  - "문자열[C++], 부동 소수점에서 변환"
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _gcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값을 문자열로 변환합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 이 버전은 보안 향상 기능이 포함된 [\_gcvt](../../c-runtime-library/reference/gcvt.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `buffer`  
 변환의 결과를 저장 하는 버퍼입니다.  
  
 \[in\] `sizeInBytes`  
 버퍼의 크기입니다.  
  
 \[in\] `value`  
 변환될 값입니다.  
  
 \[in\] `digits`  
 저장된 유효 자릿수입니다.  
  
## 반환 값  
 성공 하면 0이 됩니다.  잘못 된 매개 변수 때문에 실패 한 경우 \(잘못 된 값에 대해 다음 표 참조\) [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다.  실행을 계속 하도록 허용된 경우, 에러 코드가 반환됩니다.  오류 코드는 Errno.h에서 정의 됩니다.  이러한 오류의 목록을 보려면, 다음 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
### 오류 조건  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|반환|`buffer` 의 값입니다.|  
|--------------|-------------------|-------------|--------------|--------|----------------------|  
|`NULL`|any|any|any|`EINVAL`|수정 되지 않음|  
|`NULL` 이 아닙니다 \(유효한 메모리 포인트\)|0|any|any|`EINVAL`|수정 되지 않음|  
|`NULL` 이 아닙니다 \(유효한 메모리 포인트\)|any|any|\>\= `sizeInBytes`|`EINVAL`|수정 되지 않음|  
  
 **보안 문제**  
  
 `buffer` 가 올바른 메모리를 가르키지 않고 `NULL` 이 아닌 경우, `_gcvt_s` 는 액세스 위반을 발생할 수 있습니다.  
  
## 설명  
 `_gcvt_s` 함수는 부동 소수점 `value` 을 문자열로 변환하고 \(10진수 및 부호 가능한 바이트 포함\) `buffer` 에 문자열을 저장합니다.  `buffer` 는 변환된 된 값을 더한 자동으로 추가 되는 종료 null 문자를 수용 하기에 충분 해야 합니다.  `_CVTBUFSIZE` 길이의 버퍼는 부동 소수점 값에 대해 충분해야 합니다.  `digits` \+1 의 버퍼 사이즈가 사용 되는 경우, 함수는 버퍼의 끝을 덮어 쓰지 않습니다. 그러므로 해당 작업에 대해 충분한 버퍼를 제공해야 합니다.  `_gcvt_s` 는 10 진수 형식으로 `digits` 숫자를 생성하려고 시도합니다.  할수 없는 경우, 지수 형식의 `digits` 숫자를 생성합니다.  트레일링 제로가 변환에서 억제 될 수 있습니다.  
  
 C\+\+에서 이 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요가 없습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_gcvt_s`|\<stdlib.h\>|\<error.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Converted value: 1.2**   
## 해당 .NET Framework 항목  
 <xref:System.Convert.ToString%2A>  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)