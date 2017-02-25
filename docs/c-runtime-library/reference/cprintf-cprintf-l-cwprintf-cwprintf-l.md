---
title: "_cprintf, _cprintf_l, _cwprintf, _cwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwprintf_l"
  - "_cprintf_l"
  - "_cwprintf"
  - "_cprintf"
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
  - "_cwprintf"
  - "cwprintf"
  - "tcprintf"
  - "_tcprintf"
  - "_cprintf"
  - "cwprintf_l"
  - "tcprintf_l"
  - "_tcprintf_l"
  - "cprintf_l"
  - "_cprintf_l"
  - "_cwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cprintf 함수"
  - "_cprintf_l 함수"
  - "_cwprintf 함수"
  - "_cwprintf_l 함수"
  - "_tcprintf 함수"
  - "_tcprintf_l 함수"
  - "문자, 콘솔로 인쇄"
  - "cprintf_l 함수"
  - "cwprintf 함수"
  - "cwprintf_l 함수"
  - "콘솔로 문자 인쇄"
  - "tcprintf 함수"
  - "tcprintf_l 함수"
ms.assetid: 67ffefd4-45b3-4be0-9833-d8d26ac7c4e2
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# _cprintf, _cprintf_l, _cwprintf, _cwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

서식을 지정하고 콘솔에 출력합니다.  더 안전한 버전을 사용할 수 있습니다. [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md) 를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _cprintf(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_l(   
   const char * format,  
   locale_t locale [,  
   argument] …   
);  
int _cwprintf(  
   const wchar * format [,   
   argument] …  
);  
int _cwprintf_l(  
   const wchar * format,  
   locale_t locale [,   
   argument] …  
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
 출력된 문자의 수입니다.  
  
## 설명  
 이러한 `` 함수는 출력 문자에 대해 `_putch` 함수를 사용하여 \( `_cwprintf`에 대한`_putwch` \) 서식을 지정하고 일련의 문자와 값을 콘솔에 직접 출력합니다.  각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다.   [printf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) 함수에 대해 포맷은 `format` 매개 변수와 같은 양식과 함수를 가집니다.   `fprintf`, `printf`, 및 `sprintf` 와 다르게 `_cprintf` 또는 `_cwprintf` 는 출력시 line\-feed 문자를 캐리지 return\-line feed\(CR\-LF\) 조합으로 변환하지 않습니다.  
  
 중요 한 차이점은 `_cwprintf` 가 Windows NT 사용되는 경우 유니코드 문자를 표시한다는 것입니다.   `_cprintf` 와 달리, `_cwprintf` 는 현재 콘솔 로캘 설정을 사용합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 `_cprintf` 는 `format` 매개 변수의 유효성을 검사합니다.   `format` 이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcprintf`|`_cprintf`|`_cprintf`|`_cwprintf`|  
|`_tcprintf_l`|`_cprintf_l`|`_cprintf_l`|`_cwprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_cprintf`,`_cprintf_l`|\<conio.h\>|  
|`_cwprintf`, `_cwprintf_l`|\<conio.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
  **\-16  001d  62511  A Test**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)   
 [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)