---
title: "_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l | Microsoft Docs"
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
  - "_vcprintf_s"
  - "_vcprintf_s_l"
  - "_vcwprintf_s"
  - "_vcwprintf_s_l"
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
  - "vcprintf_s"
  - "vcwprintf_s_l"
  - "_vcwprintf_s"
  - "_vcwprintf_s_l"
  - "_vcprintf_s_l"
  - "_vtcprintf_s"
  - "vcwprintf_s"
  - "vcprintf_s_l"
  - "_vcprintf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vcprintf_s 함수"
  - "_vcprintf_s_l 함수"
  - "_vcwprintf_s 함수"
  - "_vcwprintf_s_l 함수"
  - "_vtcprintf_s 함수"
  - "_vtcprintf_s_l 함수"
  - "서식 있는 텍스트[C++]"
  - "vcprintf_s 함수"
  - "vcprintf_s_l 함수"
  - "vcwprintf_s 함수"
  - "vcwprintf_s_l 함수"
  - "vtcprintf_s 함수"
  - "vtcprintf_s_l 함수"
ms.assetid: 5a46d45a-30db-45df-9850-455cbdac5636
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

쓰기는 인수 목록에 대한 포인터를 사용하여 콘솔에 출력을 포맷 합니다.  이러한 버전의 [\_vcprintf, \_vcprintf\_l, \_vcwprintf, \_vcwprintf\_l](../../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _vcprintf(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_s(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_s_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### 매개 변수  
 `format`  
 형식 사양입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 반환 값  
 인쇄된 문자 수를 반환하거나 오류가 발생하면 음수 값을 반환합니다.  
  
 이러한 함수의 보안 버전처럼, `format` null 포인터가 잘못 된 경우, 매개 변수 처리기 호출에서 설명한 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)입니다.  또한 이러한 함수의 보안 버전 달리 경우 `format` 올바른 형식을 지정 하지 않으면 잘못 된 매개 변수가 예외가 생성 됩니다.  이러한 집합과 함수 반환 오류 코드가 계속 실행이 허용 되는 경우 `errno` 해당 오류 코드를 설정합니다.  구체적인 값을 적용 하지 않는 경우, 기본 오류 코드는 `EINVAL` 입니다.  
  
## 설명  
 이러한 함수의 각각은 인수 목록에 대한 포인터를 가지며, 서식을 지정하고 지정된 데이터를 가르키는 메모리에 작성합니다.  `_vcwprintf_s` 는 `_vcprintf_s` 의 와이드 문자 버전입니다.  와이드 문자 문자열을 인수로 걸립니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtcprintf_s`|`_vcprintf_s`|`_vcprintf_s`|`_vcwprintf_s`|  
|`_vtcprintf_s_l`|`_vcprintf_s_l`|`_vcprintf_s_l`|`_vcwprintf_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_vcprintf_s`, `_vcprintf_s_l`|\<conio.h\> 및 \<stdarg.h\>|\<varargs.h\>\*|  
|`_vcwprintf_s`, `_vcwprintf_s_l`|\<stdio.h\> 또는 \<wchar.h\>, 및 \<stdarg.h\>|\<varargs.h\>\*|  
  
 \*는 UNIX V 호환성을 위해 필요합니다.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_vcprintf_s.cpp  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function used to print to the console.  
int eprintf_s(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf_s(format, args);  
}  
  
int main()  
{  
   eprintf_s("  (%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,  
           "<some error text>");  
   eprintf_s("  (Related to symbol '%s' defined on line %d).\n",  
           "<symbol>", 5 );  
}  
```  
  
  **\(10,23\): 오류 C2111: \<오류 텍스트\>**  
 **\(기호 관련 '\<기호\>' 5 줄에 정의\).**   
## 해당 .NET Framework 항목  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)