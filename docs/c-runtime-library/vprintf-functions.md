---
title: "vprintf 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "서식 있는 텍스트[C++]"
  - "vprintf 함수"
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# vprintf 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각각의 `vprintf` 함수 인수 목록에 대한 포인터를 가진 다음 지정된 된 데이터를 특정 대상에 포맷하고 씁니다.  함수는 함수가 넓은 싱글 바이트 문자 스트링, 출력 목적지 및 파라미터 형식 문자열에 사용되는 순서를 지정하기위한 지원을 가지고 있는지 여부를 수행하는 파라미터 검증이 다릅니다.  
  
|||  
|-|-|  
|[\_vcprintf, \_vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[\_vscprintf, \_vscprintf\_l, \_vscwprintf, \_vscwprintf\_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[\_vsnprintf, \_vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## 설명  
 `vprintf` 함수는 다음 표에 나열 된 해당 대응 함수와 비슷합니다.  그러나 각 `vprintf` 함수는 다른 각 대응 함수가 인수 목록을 받는 반면 인수 목록을 포인터로 받습니다.  
  
 이러한 함수는 다음과 같이 출력 목적지로 데이터 서식을 지정합니다.  
  
|Function|대응 함수|출력 대상|매개 변수 유효성 검사|위치 매개 변수 지원|  
|--------------|-----------|-----------|------------------|-----------------|  
|`_vcprintf`|[\_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|콘솔|Null 있는지 확인 합니다.|no|  
|`_vcwprintf`|[\_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|콘솔|Null 있는지 확인 합니다.|no|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*스트림*|Null 있는지 확인 합니다.|no|  
|**vfprintf\_p**|[fprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*스트림*|Null 및 올바른 형식이 있는지 확인 합니다.|yes|  
|`vfprintf_s`|[fprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*스트림*|Null 및 올바른 형식이 있는지 확인 합니다.|no|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*스트림*|Null 있는지 확인 합니다.|no|  
|**vfwprintf\_p**|[fwprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*스트림*|Null 및 올바른 형식이 있는지 확인 합니다.|yes|  
|`vfwprintf_s`|[fwprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*스트림*|Null 및 올바른 형식이 있는지 확인 합니다.|no|  
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null 있는지 확인 합니다.|no|  
|**vprintf\_p**|[printf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Null 및 올바른 형식이 있는지 확인 합니다.|yes|  
|`vprintf_s`|[printf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Null 및 올바른 형식이 있는지 확인 합니다.|no|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null 있는지 확인 합니다.|no|  
|**vwprintf\_p**|[wprintf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Null 및 올바른 형식이 있는지 확인 합니다.|yes|  
|`vwprintf_s`|[wprintf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Null 및 올바른 형식이 있는지 확인 합니다.|no|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|*버퍼* 가 가르키는 메모리|Null 있는지 확인 합니다.|no|  
|**vsprintf\_p**|[sprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|*버퍼* 가 가르키는 메모리|Null 및 올바른 형식이 있는지 확인 합니다.|yes|  
|`vsprintf_s`|[sprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|*버퍼* 가 가르키는 메모리|Null 및 올바른 형식이 있는지 확인 합니다.|no|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|*버퍼* 가 가르키는 메모리|Null 있는지 확인 합니다.|no|  
|**vswprintf\_p**|[swprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|*버퍼* 가 가르키는 메모리|Null 및 올바른 형식이 있는지 확인 합니다.|yes|  
|`vswprintf_s`|[swprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|*버퍼* 가 가르키는 메모리|Null 및 올바른 형식이 있는지 확인 합니다.|no|  
|`_vscprintf`|[\_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|*버퍼* 가 가르키는 메모리|Null 있는지 확인 합니다.|no|  
|`_vscwprintf`|[\_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|*버퍼* 가 가르키는 메모리|Null 있는지 확인 합니다.|no|  
|`_vsnprintf`|[\_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|*버퍼* 가 가르키는 메모리|Null 있는지 확인 합니다.|no|  
|`_vsnwprintf`|[\_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|*버퍼* 가 가르키는 메모리|Null 있는지 확인 합니다.|no|  
  
 `argptr` 인수는 VARARGS.H and STDARG.H 에 정의된 `va_list` 형식을 가집니다.  `argptr` 변수는 **va\_start,** 에 의해 초기화 되어야 하고, `va_arg` 호출로 다시 초기화 될 수 있습니다. 그러면 `argptr` 는 *양식* 인수에 해당하는 지시에 따라 변환하고 출력을 전송하는 인수 목록의 시작부분을 가르킵니다.  *형식* 은 [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 에 대해 *형식* 인수와 같은 함수와 형식을 가집니다.  `va_end` 을 호출하는 함수 없음  각 `vprintf` 함수에 대한 자세한 설명은 위의 표에 나열 된 함수의 설명을 참조 하십시오.  
  
 `_vsnprintf` 는 *buffer* 에 *count* 바이트를 더 이상 쓰지 않는 다는 점에서 **vsprintf** 와 다릅니다.  
  
 이름에서 **w** 삽입사를 사용하는 이러한 함수의 버전은 **w** 삽입사가 없는 대응 함수의 와이드 문자 버전입니다. 이러한 와이드 문자 함수의 각각에서 *buffer* 및 *양식* 은 와이드 문자 문자열입니다.  그렇지 않으면 각 와이드 문자 함수는 해당 SBCS 대응 기능을 동일 하게 동작합니다.  
  
 **\_s** 및 **\_p** 접미사를 사용하는 이러한 함수의 버전은 더 안전한 버전입니다.  이러한 버전은 형식 문자열의 유효성을 검사 하고 형식 문자열 형식이 잘못 된 경우\(예를 들어 잘못 된 서식 문자를 사용하는\) 예외가 발생 합니다.  
  
 **\_p** 접미사를 사용하는 이러한 함수의 버전은 형식 문자열에 제공된 인수 대신 순서를 지정할 수 있는 기능을 제공 합니다.  자세한 내용은 [printf\_p 위치 매개 변수](../c-runtime-library/printf-p-positional-parameters.md)을 참조하십시오.  
  
 **vsprintf**, `vswprintf`, `_vsnprintf` 및 `_vsnwprintf` 에 대해 중복 되는 문자열 간에 복사가 이루어지면, 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  *형식* 이 사용자 정의 문자열이 아닌지 확인하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  이러한 함수의 보안 버전을 사용 하는 경우 \(**\_s** 또는 **\_p** 접미사도 마찬가지로\), 사용자 제공 문자열에 잘못 된 문자가 포함 되어 있는 경우 사용자 지정 형식 문자열을 매개 변수에 잘못 된 예외를 트리거할 수 있습니다.  
  
## 참고 항목  
 [스트림 I\/O](../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)