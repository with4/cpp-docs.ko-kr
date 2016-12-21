---
title: "_mbccpy, _mbccpy_l | Microsoft Docs"
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
  - "_mbccpy"
  - "_mbccpy_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbccpy"
  - "tccpy"
  - "ftccpy"
  - "mbccpy"
  - "_tccpy"
  - "_ftccpy"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbccpy 함수"
  - "_mbccpy_l 함수"
  - "_tccpy 함수"
  - "_tccpy_l 함수"
  - "mbccpy 함수"
  - "mbccpy_l 함수"
  - "tccpy 함수"
  - "tccpy_l 함수"
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbccpy, _mbccpy_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

한 문자열에서 다른 문자열을 멀티 바이트 문자를 복사합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_mbccpy\_s, \_mbccpy\_s\_l](../../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
void _mbccpy(  
   unsigned char *dest,  
   const unsigned char *src   
);  
void _mbccpy_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `dest`  
 대상에 복사 합니다.  
  
 `src`  
 멀티 바이트 문자를 복사 합니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 설명  
 `_mbccpy` 함수는 하나의 멀티 바이트 문자를 `src` 에서 `dest`까지 복사합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  만약 `_mbccpy` 이 `dest` 또는 `src`에 대해 널포인터로 진행될 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)으로 설명되며, 타당한 매개변수 처리기가 호출됩니다.  실행을 계속 허용 되는 경우 `errno` 는 `EINVAL` 을 설정합니다.  
  
 `_mbccpy`는 로캘 종속 동작의 현재 로캘을 사용합니다.  `_mbccpy_l` 는 `_mbccpy` 와 동일합니다. 여기서 `_mbccpy_l` 모든 로캘 종속 동작에 대해 전달 된 로캘을 사용하는것을 제외합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 **보안 정보** 는 null로 끝나는 문자열을 사용 합니다.  Null로 끝나는 문자열 대상 버퍼의 크기를 초과할 수 없습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tccpy`|매크로 또는 인라인 함수에 매핑|`_mbccpy`|매크로 또는 인라인 함수에 매핑|  
|`_tccpy_l`|해당 없음|`_mbccpy_l`|해당 없음|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbccpy`|\<mbctype.h\>|  
|`_mbccpy_l`|\<mbctype.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)