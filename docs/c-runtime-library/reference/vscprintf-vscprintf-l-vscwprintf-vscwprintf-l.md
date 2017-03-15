---
title: "_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vscprintf"
  - "_vscprintf_l"
  - "_vscwprintf_l"
  - "_vscwprintf"
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
  - "vscprintf_l"
  - "vscwpeintf"
  - "_vscwprintf"
  - "_vsctprintf"
  - "_vscprintf"
  - "vscwprintf_l"
  - "vscprintf"
  - "_vscwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vscprintf 함수"
  - "_vscprintf_l 함수"
  - "_vsctprintf 함수"
  - "_vsctprintf_l 함수"
  - "_vscwprintf 함수"
  - "_vscwprintf_l 함수"
  - "서식 있는 텍스트[C++]"
  - "vscprintf 함수"
  - "vscprintf_l 함수"
  - "vsctprintf 함수"
  - "vsctprintf_l 함수"
  - "vscwprintf 함수"
  - "vscwprintf_l 함수"
ms.assetid: 1bc67d3d-21d5-49c9-ac8d-69e26b16a3c3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용 하여 서식이 지정 된 문자열에서의 문자 수를 반환 합니다.  
  
## 구문  
  
```  
int _vscprintf(  
   const char *format,  
   va_list argptr   
);  
int _vscprintf_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vscwprintf(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vscwprintf_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### 매개 변수  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 반환 값  
 `_vscprintf` 는 인쇄 되었거나 파일이나 지정 된 형식 지정 코드를 사용하여 버퍼에 보낼 인수 목록에서 문자열을 가르킬 경우 생성 되는 문자의 수를 반환합니다.  반환 값은 null 종결 문자를 포함 하지 않습니다.  `_vscwprintf` 는 와이드 문자에 대해 동일한 기능을 수행합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 `format` 이 null 포인터인 경우, 설명된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
## 설명  
 각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환됩니다.  형식은 일반 문자로 구성되어 있으며, [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 위한 `format` 인수와 동일한 형태와 기능을 가지고 있습니다.  
  
> [!IMPORTANT]
>  `format` 가 사용자 정의 문자열인 경우 확인하십시오. null 종료자이고 올바른 수와 매개 변수 형식을 가집니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vsctprintf`|`_vscprintf`|`_vscprintf`|`_vscwprintf`|  
|`_vsctprintf_l`|`_vscprintf_l`|`_vscprintf_l`|`_vscwprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_vscprintf`, `_vscprintf_l`|\<stdio.h\>|  
|`_vscwprintf`, `_vscwprintf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 예제를 보려면 [vsprintf](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md) 을 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)