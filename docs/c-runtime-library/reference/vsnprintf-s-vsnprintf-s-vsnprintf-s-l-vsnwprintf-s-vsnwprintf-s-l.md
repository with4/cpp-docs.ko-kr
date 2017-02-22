---
title: "vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsnwprintf_s"
  - "_vsnwprintf_s_l"
  - "_vsnprintf_s"
  - "vsnprintf_s"
  - "_vsnprintf_s_l"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf_s"
  - "_vsntprintf_s"
  - "_vsnwprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vsnprintf_s 함수"
  - "_vsnprintf_s_l 함수"
  - "_vsntprintf_s 함수"
  - "_vsntprintf_s_l 함수"
  - "_vsnwprintf_s 함수"
  - "_vsnwprintf_s_l 함수"
  - "서식 있는 텍스트[C++]"
  - "vsnprintf_s 함수"
  - "vsnprintf_s_l 함수"
  - "vsntprintf_s 함수"
  - "vsntprintf_s_l 함수"
  - "vsnwprintf_s 함수"
  - "vsnwprintf_s_l 함수"
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용하여 서식이 지정된 출력을 작성합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [vsnprintf, \_vsnprintf, \_vsnprintf\_l, \_vsnwprintf, \_vsnwprintf\_l](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) 버전입니다.  
  
## 구문  
  
```  
int vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int _vsnprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치입니다.  
  
 `sizeOfBuffer`  
 `buffer` 의 출력 크기, 문자 수와 같이.  
  
 `count`  
 작성하기 위한 최대 문자 수\(종료 null 포함 하지 않음\), 또는 [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `format`  
 형식 사양입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 반환 값  
 `vsnprintf_s`,`_vsnprintf_s` and `_vsnwprintf_s` 는 NULL 문자로 끝나거나 오류가 발생한 경우의 네이티브 값을 제외한 작성된 문자의 수를 반환합니다.  `vsnprintf_s` 는 `_vsnprintf_s`와 동일합니다.  `vsnprintf_s` 는 ANSI 표준 준수에 대해 포함되어 있습니다.  `_vnsprintf` 클래스는 이전 버전과의 호환성을 위해 유지됩니다.  
  
 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된대로 종료 null 데이터를 저장 하는데 필요한 스토리지가 `sizeOfBuffer`을 초과 하는 경우 잘못된 매개 변수 처리기를 호출할 하지 않는 한 `count` 가 문자열이 많이 들어가는 [\_TRUNCATE](../../c-runtime-library/truncate.md) 이 되지 않는 한 `buffer` 가 작성되고 \-1이 반환 됩니다.  잘못된 매개 변수 처리기 이후에 실행이 계속되는 경우 이러한 함수는 `buffer` 은 빈 문자열로 설정하고 `errno` 를 `ERANGE`로 설정하고 \-1을 반환합니다.  
  
 만약 `buffer` 또는 `format` 가 `NULL` 포인터인 경우 또는 `count` 가 0보다 작거나 같은 값인 경우 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  
  
### 오류 조건  
  
|`Condition`|반환|`errno`|  
|-----------------|--------|-------------|  
|`buffer` 가 `NULL`입니다.|\-1|`EINVAL`|  
|`format` 가 `NULL`입니다.|\-1|`EINVAL`|  
|`count` \<\= 0|\-1|`EINVAL`|  
|`sizeOfBuffer` 너무 작음 \(그리고 `count` \!\= `_TRUNCATE`\)|\-1 \(및 `buffer` 를 빈 문자열로 설정한 경우\)|`ERANGE`|  
  
## 설명  
 각 함수는 포인터를 인수 목록에 가져가고 `buffer` 로 주어진 데이터를 메모리에 다음과 같은 `count` 문자로 서식화하고 기록하며 종료 null을 추가합니다.  
  
 만약 `count` 이 [\_TRUNCATE](../../c-runtime-library/truncate.md)일 경우 이러한 함수는 `buffer` 에 문자열이 들어갈 수 있을 만큼 많이 기록하며 종료 null에 대한 공간을 두고 있습니다.  전체 문자열\(종료 null 포함\)이 `buffer`에 맞는 경우, 이러한 함수는 작성된 \(종료 null 포함 하지 않음\) 문자의 수를 반환합니다. 그렇지 않으면 이들 함수는 \-1을 출력하여 잘리는 현상이 표시 되었음을 알립니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
> [!NOTE]
>  종료 null에 대한 공간이 있음을 확실히 하기 위해 `count` 가 버퍼 길이 보다 작다는 것을 확인하거나 `_TRUNCATE`을 사용하세요.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vsntprintf_s`|`_vsnprintf_s`|`_vsnprintf_s`|`_vsnwprintf_s`|  
|`_vsntprintf_s_l`|`_vsnprintf_s_l`|`_vsnprintf_s_l`|`_vsnwprintf_s_l`|  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`vsnprintf_s`|\<stdio.h\> 과 \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnprintf_s`, `_vsnprintf_s_l`|\<stdio.h\> 과 \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnwprintf_s`, `_vsnwprintf_s_l`|\<stdio.h\> 또는 \<wchar.h\>, 및 \<stdarg.h\>|\<varargs.h\>\*|  
  
 \*는 UNIX V 호환성을 위해 필요합니다.  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_vsnprintf_s.cpp  
#include <stdio.h>  
#include <wtypes.h>  
  
void FormatOutput(LPCSTR formatstring, ...)   
{  
   int nSize = 0;  
   char buff[10];  
   memset(buff, 0, sizeof(buff));  
   va_list args;  
   va_start(args, formatstring);  
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);  
   printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
   FormatOutput("%s %s", "Hi", "there");  
   FormatOutput("%s %s", "Hi", "there!");  
   FormatOutput("%s %s", "Hi", "there!!");  
}  
```  
  
  **nSize: 8, 버프: 안녕**  
**nSize: 9, 버프: 안녕\!**  
**nSize: \-1, 버프: 안녕\!**   
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)