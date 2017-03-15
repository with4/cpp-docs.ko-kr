---
title: "_MBCS 코드와 TCHAR.H 데이터 형식 사용 | Microsoft Docs"
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
  - ""tchar.h""
  - "TCHAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "일반 텍스트 데이터 형식[C++]"
  - "일반 텍스트 매핑[C++]"
  - "일반 텍스트 매핑"
  - "매핑[C++], TCHAR.H"
  - "MBCS[C++], 일반 텍스트 매핑"
  - "TCHAR.H 데이터 형식, 매핑"
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# _MBCS 코드와 TCHAR.H 데이터 형식 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

명시적 상수인 **\_MBCS**가 정의되면 지정된 일반 텍스트 루틴은 다음 루틴 유형 중 하나에 매핑됩니다.  
  
-   멀티바이트로 된 바이트, 문자 및 문자열을 적절하게 처리하는 SBCS 루틴.  이 경우 문자열 인수 형식은 **char\***가 됩니다.  예를 들어, `_tprintf`는 `printf`에 매핑됩니다. `printf`의 문자열 인수는 **char\*** 형식입니다.  문자열 형식에 **\_TCHAR** 일반 텍스트 데이터 형식을 사용하면 **\_TCHAR**\*가 **char\***에 매핑되기 때문에 `printf`의 형식 매개 변수 형식과 실제 매개 변수 형식은 일치합니다.  
  
-   MBCS 관련 루틴.  이 경우 문자열 인수 형식은 `unsigned` **char\***가 됩니다.  예를 들어, `_tcsrev`는 `unsigned` **char\***  형식의 문자열을 예상 및 반환하는 `_mbsrev`에 매핑됩니다.  문자열 형식에 **\_TCHAR** 일반 텍스트 데이터 형식을 사용하면 **\_TCHAR**가 `char` 형식에 매핑되기 때문에 형식이 충돌할 수 있습니다.  
  
 다음 세 가지 방법을 사용하면 이러한 형식 충돌 및 그로 인한 C 컴파일러 경고 또는 C\+\+ 컴파일러 오류를 방지할 수 있습니다.  
  
-   기본 동작을 사용합니다.  Tchar.h는 다음 예제와 같이 런타임 라이브러리의 루틴에 일반 텍스트 루틴 프로토타입을 제공합니다.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     기본 동작에서 `_tcsrev`의 프로토타입은 Libc.lib의 썽크를 통해 `_mbsrev`에 매핑됩니다.  그러면 들어오는 매개 변수 `_mbsrev`와 **\_TCHAR \***에서 나가는 반환 값의 형식\(즉, `char` **\***\)이 `unsigned` `char` **\***로 변경됩니다.  이 방법은 **\_TCHAR**를 사용할 경우 형식은 일치되지만 함수 호출 오버헤드로 인해 비교적 속도가 느립니다.  
  
-   코드에 다음 전처리기 명령문을 병합하여 인라인 함수를 사용합니다.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     이 방법을 사용하면 Tchar.h에 제공된 인라인 함수 썽크가 일반 텍스트 루틴을 직접 해당 MBCS 루틴에 매핑합니다.  Tchar.h에서 발췌한 다음 코드는 이 과정을 설명하는 예제입니다.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     인라이닝은 형식을 일치시키고 시간이 추가로 소요되지 않으므로 사용가능한 경우 최상의 방법입니다.  
  
-   코드에 다음 전처리기 명령문을 병합하여 직접 매핑을 사용합니다.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     이것은 기본 동작을 사용하지 않거나 인라이닝을 사용할 수 없을 경우에 유용한 빠른 방법입니다.  이 방법을 사용하면 Tchar.h에서 발췌한 다음 예제와 같이 매크로가 루틴의 MBCS 버전에 일반 텍스트 루틴을 직접 매핑합니다.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     이 접근 방법을 선택할 경우 문자열 인수와 문자열 반환값에 적절한 데이터 형식을 사용하도록 주의해야 합니다.  형식 변환을 사용하여 확실하게 형식이 일치하도록 하거나 **\_TXCHAR** 일반 텍스트 데이터 형식을 사용할 수 있습니다.  **\_TXCHAR**는 SBCS 코드에서 `char` 형식에 매핑되지만 MBCS 코드에서는 `unsigned` `char` 형식에 매핑됩니다.  일반 텍스트 매크로에 대한 자세한 내용은 *Run\-Time Library Reference*의 [Generic\-Text Mappings](../c-runtime-library/generic-text-mappings.md)을 참조하십시오.  
  
## 참고 항목  
 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)