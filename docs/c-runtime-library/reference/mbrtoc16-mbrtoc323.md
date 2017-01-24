---
title: "mbrtoc16, mbrtoc32 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbrtoc16"
  - "mbrtoc32"
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
  - "mbrtoc16"
  - "mbrtoc32"
  - "uchar/mbrtoc16"
  - "uchar/mbrtoc32"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "mbrtoc16 함수"
  - "mbrtoc32 함수"
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbrtoc16, mbrtoc32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

반각 문자열의 첫 번째 멀티바이트 문자를 해당하는 UTF\-16 또는 UTF\-32 문자로 변환합니다.  
  
## 구문  
  
```  
size_t mbrtoc16(   
   char16_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
size_t mbrtoc32(  
   char32_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
```  
  
#### 매개 변수  
 `destination`  
 변환할 멀티바이트 문자에 해당하는 `char16_t` 또는 `char32_t` 문자의 포인터입니다. Null인 경우 함수는 값을 저장하지 않습니다.  
  
 `source`  
 변환할 멀티바이트 문자열의 포인터입니다.  
  
 `max_bytes`  
 변환할 문자에 대해 검사할 `source`의 최대 바이트 수입니다. 1과 `source`에 남아 있는 바이트\(null 종결자 포함\) 수 사이의 값이어야 합니다.  
  
 `state`  
 멀티바이트 문자열을 하나 이상의 출력 문자로 해석하는 데 사용되는 `mbstate_t` 변환 상태 개체의 포인터입니다.  
  
## 반환 값  
 성공 시, 현재 `state` 값이 다음과 같을 때 적용되는 아래 조건 중 첫 번째 값이 반환됩니다.  
  
|값|조건|  
|-------|--------|  
|0|`source`에서 변환되는 다음 `max_bytes` 이하 문자는 null 와이드 문자에 해당하며, 이는 `destination`이 null이 아닌 경우 저장되는 값입니다.<br /><br /> `state`에는 초기 이동 상태가 포함되어 있습니다.|  
|1과 `max_bytes`\(포함\) 사이|반환되는 값은 유효한 멀티바이트 문자를 완성하는 `source`의 바이트 수입니다.`destination`이 null이 아닌 경우 변환된 와이드 문자가 저장됩니다.|  
|\-3|`destination`이 null이 아닌 경우 함수에 대한 이전 호출로 발생하는 다음 와이드 문자가 `destination`에 저장되어 있습니다.`source`의 바이트는 함수에 대한 이 호출에서 사용되지 않습니다.<br /><br /> `source`에서 두 개 이상의 와이드 문자가 나타내야 하는 멀티바이트 문자\(예: 서로게이트 쌍\)를 가리키면 다음 함수 호출에서 추가 문자를 작성하도록 `state` 값이 업데이트됩니다.|  
|\-2|다음 `max_bytes` 바이트는 완료되지 않았지만 잠재적으로 유효한 멀티바이트 문자를 나타냅니다.`destination`에 저장된 값이 없습니다. 이 결과는 `max_bytes`가 0인 경우에 발생할 수 있습니다.|  
|\-1|인코딩 오류가 발생했습니다. 다음 `max_bytes`개 이하의 바이트가 완전하며 올바른 멀티바이트 문자에 포함되지 않습니다.`destination`에 저장된 값이 없습니다.<br /><br /> `EILSEQ`가 `errno`에 저장되며, 변환 상태 `state`는 지정되지 않습니다.|  
  
## 주의  
 `mbrtoc16` 함수는 `source`에서 `max_bytes`바이트까지 읽어 완전하고 유효한 첫 번째 멀티바이트 문자를 찾은 후 해당하는 UTF\-16 문자를 `destination`에 저장합니다. 소스 바이트는 현재 스레드 멀티바이트 로캘에 따라 해석됩니다. 멀티바이트 문자에서 서로게이트 쌍과 같은 둘 이상의 UTF\-16 출력 문자가 필요하면 `state` 값이 `mbrtoc16`에 대한 다음 호출 시 `destination`에 다음 UTF\-16 문자를 저장하도록 설정됩니다.`mbrtoc32` 함수는 동일하지만, 출력이 UTF\-32 문자로 저장됩니다.  
  
 `source`가 null인 경우 이러한 함수는 `destination`에 `NULL`, `source`에 `""`, `max_bytes`에 `1`의 인수를 사용한 호출에 해당하는 값을 반환합니다.`destination` 및 `max_bytes`의 전달된 값은 무시됩니다.  
  
 `source`가 null인 아닌 경우 함수는 문자열의 맨 앞에서 시작하고 `max_bytes`바이트까지 검사하여 다음 멀티바이트 문자를 완성하는 데 필요한 바이트 수를 결정합니다\(이동 시퀀스 포함\). 검사된 바이트에 유효하고 완전한 멀티바이트 문자가 포함되는 경우 함수는 문자를 해당하는 16비트 또는 32비트 와이드 문자로 변환합니다.`destination`이 null이 아닌 경우 함수는 대상의 첫 번째\(그리고 유일할 수 있음\) 결과 문자를 저장합니다. 추가 출력 문자가 필요한 경우 값이 `state`에 설정되므로 함수에 대한 후속 호출에서 추가 문자를 출력하고 \-3 값을 반환합니다. 출력 문자가 더 이상 필요하지 않으면 `state`가 초기 이동 상태로 설정됩니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`mbrtoc16`, `mbrtoc32`|\<uchar.h\>|\<cuchar\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [c16rtomb, c32rtomb](../../c-runtime-library/reference/c16rtomb-c32rtomb1.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md)   
 [mbsrtowcs\_s](../../c-runtime-library/reference/mbsrtowcs-s.md)