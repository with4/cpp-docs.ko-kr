---
title: "_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "fmode"
  - "_fmode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "파일 변환[C++], 기본 모드"
  - "fmode 함수"
  - "_fmode 함수"
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_fmode`변수는 텍스트 또는 이진 변환에 대해 기본적인 파일 변환 모드를 설정합니다.  이 전역 변수는 전역 변수 대신에 사용 될 수 있는 보안 기능이 강화된 버전의 함수인 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) 및 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)에서는 종료됩니다.  이것은 Stdlib.h에서 다음과 같이 선언됩니다.  
  
## 구문  
  
```  
extern int _fmode;  
```  
  
## 설명  
 텍스트 모드 변환에 대해 `_fmode`  의 기본 설정은 `_O_TEXT`  입니다.  `_O_BINARY` 는 이진 모드에 대한 설정입니다.  
  
 세가지 방식으로 `_fmode` 의 값을 변경할 수 있습니다:  
  
-   Binmode.obj를 사용하여 연결합니다.  이것은 `_fmode` 의 초기 설정을 `_O_BINARY` 로 변경하는데 이진 모드에서 열기위해 `stdin`, `stdout`와 `stderr` 을 제외한 모든 파일을 야기합니다.  
  
-   각각 `_fmode` 전역 변수를 설정하거나 얻기위해 `_get_fmode` 또는 `_set_fmode` 을 호출합니다.  
  
-   프로그램에서 이것을 직접 설정함으로써 `_fmode` 의 값을 변경합니다.  
  
## 참고 항목  
 [전역 변수](../c-runtime-library/global-variables.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)