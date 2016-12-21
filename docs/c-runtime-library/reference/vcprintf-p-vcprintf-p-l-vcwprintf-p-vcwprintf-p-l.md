---
title: "_vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vcprintf_p"
  - "_vcwprintf_p_l"
  - "_vcprintf_p_l"
  - "_vcwprintf_p"
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
  - "vcwprintf_p"
  - "vcprintf_p_l"
  - "_vcprintf_p"
  - "_vcprintf_p_l"
  - "vcwprintf_p_l"
  - "vcprintf_p"
  - "_vcwprintf_p"
  - "_vcwprintf_p_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vcprintf_p 함수"
  - "_vcprintf_p_l 함수"
  - "_vcwprintf_p 함수"
  - "_vcwprintf_p_l 함수"
  - "_vtcprintf_p 함수"
  - "_vtcprintf_p_l 함수"
  - "vcprintf_p 함수"
  - "vcprintf_p_l 함수"
  - "vcwprintf_p 함수"
  - "vcwprintf_p_l 함수"
  - "vtcprintf_p 함수"
  - "vtcprintf_p_l 함수"
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용하여 서식 있는 출력을 콘솔에 기록하고 형식 문자열에서 위치 매개 변수를 지원합니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
int _vcprintf_p(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_p_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_p(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_p_l(  
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
  
 자세한 내용은 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.  
  
## 반환 값  
 기록된 문자 수 또는 출력 오류가 발생하는 경우 음수 값입니다.  `format`이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 \-1이 반환됩니다.  
  
## 설명  
 이러한 각 함수는 인수 목록에 대한 포인터를 가져온 다음 `_putch` 함수를 사용하여 주어진 데이터의 서식을 지정하고 이 데이터를 콘솔에 기록합니다.  \(`_vcwprintf_p`는 `_putch` 대신 `_putwch`를 사용합니다.  `_vcwprintf_p`는 `_vcprintf_p`의 와이드 문자 버전입니다.  인수로 와이드 문자열이 필요합니다.\)  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용한다는 점만 제외하고 모두 동일합니다.  
  
 각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다.  형식 사양은 인수가 형식 문자열에서 사용되는 순서를 지정할 수 있도록 위치 매개 변수를 지원합니다.  자세한 내용은 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.  
  
 이러한 함수는 출력될 때 줄 바꿈 문자를 CR\-LF\(캐리지 리턴 줄 바꿈\) 조합으로 변환하지 않습니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하세요.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
 이 함수는 입력 포인터와 형식 문자열의 유효성을 검사합니다.  `format` 또는 `argument`가 `NULL`이거나 형식 문자열에 잘못된 형식 지정 문자가 포함되어 있는 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우 이러한 함수가 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtcprintf_p`|`_vcprintf_p`|`_vcprintf_p`|`_vcwprintf_p`|  
|`_vtcprintf_p_l`|`_vcprintf_p_l`|`_vcprintf_p_l`|`_vcwprintf_p_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_vcprintf_p`, `_vcprintf_p_l`|\<conio.h\> 및 \<stdarg.h\>|  
|`_vcwprintf_p`, `_vcwprintf_p_l`|\<conio.h\> 및 \<stdarg.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_vcprintf_p.c  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function that's used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf_p(format, args);  
}  
  
int main()  
{  
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",  
      "one", 222);  
   _cprintf_s("%d characters printed\r\n");  
}  
```  
  
  **매개 변수 2 \= 222; 매개 변수 1 \= 1**  
**인쇄되는 글자 38자**   
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)