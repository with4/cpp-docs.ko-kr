---
title: "_set_controlfp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_controlfp"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_controlfp"
  - "_set_controlfp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_controlfp 함수"
  - "부동 소수점 함수, 제어 단어 설정"
  - "set_controlfp 함수"
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _set_controlfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 제어 단어를 설정합니다.  
  
## 구문  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### 매개 변수  
 `newControl`  
 새 컨트롤 단어 비트 값입니다.  
  
 `mask`  
 새 컨트롤 단어 비트를 설정하기 위한 마스크입니다.  
  
## 반환 값  
 없음  
  
## 설명  
 `_set_controlfp` 는 `_control87` 와 유사하지만, 오직 `newControl` 로 부동 소수점 제어 단어를 설정합니다.  값의 비트 부동 소수점 제어 상태를 나타냅니다.  부동 소수점 제어 상태는 부동 소수점 math 패키지에서 무한대 모드와 반올림, 정밀도를 변경하기위한 프로그램을 허용합니다.  또한 `_set_controlfp` 부동 소수점 예외를 감추거나 나타내기 위해 사용할 수 있습니다.  자세한 내용은 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)을 참조하십시오.  
  
 공용 언어 런타임은 오직 기본 부동 소수점 정밀도만을 지원하기 때문에 이러한 함수는 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 또는 `/clr:pure` 를 사용하여 컴파일하는 경우 무시됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|호환성|  
|--------|-----------|---------|  
|`_set_controlfp`|\<float.h\>|x86 프로세서만|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)