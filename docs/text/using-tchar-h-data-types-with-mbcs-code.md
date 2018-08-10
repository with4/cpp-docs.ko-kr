---
title: TCHAR를 사용합니다. _MBCS 코드와 시간 데이터 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- tchar.h
- TCHAR
dev_langs:
- C++
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3aa2f0dffd33f0ac885753e4c7fb7f413d755149
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020329"
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS 코드와 TCHAR.H 데이터 형식 사용
경우 매니페스트 상수 `_MBCS` 는 지정 된 제네릭 텍스트 루틴 정의 다음 종류의 루틴 중 하나에 매핑됩니다.  
  
-   멀티바이트 바이트, 문자 및 문자열을 적절하게 처리하는 SBCS 루틴. 이 경우 문자열 인수는 `char*` 형식이어야 합니다. 예를 들어 `_tprintf`는 `printf`에 매핑되고 `printf`에 대한 문자열 인수는 `char*` 형식입니다. 문자열 형식에 대해 `_TCHAR` 일반 텍스트 데이터 형식을 사용하는 경우 `_TCHAR*`이 `char*`에 매핑되므로 `printf`에 대한 형식 및 실제 매개 변수 형식은 일치합니다.  
  
-   MBCS 관련 루틴. 이 경우 문자열 인수는 `unsigned char*` 형식이어야 합니다. 예를 들어 `_tcsrev`는 `unsigned char*` 형식의 문자열을 사용하고 반환하는 `_mbsrev`에 매핑됩니다. 사용 하는 경우는 `_TCHAR` 때문에 잠재적인 형식 충돌이 발생 문자열 형식에 대 한 일반 텍스트 데이터 형식 `_TCHAR` 형식에 매핑되므로 `char`합니다.  
  
 이러한 형식 충돌(및 이로 인한 C 컴파일러 경고 또는 C++ 컴파일러 오류)을 방지하기 위한 방법으로는 다음 세 가지가 있습니다.  
  
-   기본 동작을 사용합니다. Tchar.h는 다음 예제와 같이 런타임 라이브러리의 루틴에에서 일반 텍스트 루틴 프로토타입을 제공합니다.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     기본 경우에 대 한 프로토타입 `_tcsrev` 매핑됩니다 `_mbsrev` Libc.lib의 썽크를 통해. 형식을 변경 합니다 `_mbsrev` 들어오는 매개 변수 및 나가는 반환 값 `_TCHAR*` (즉, `char *`)를 `unsigned char *`합니다. 이 방법을 사용 하는 경우 형식 일치를 사용 하면 `_TCHAR`, 하지만 함수 호출 오버 헤드로 인해 속도가 비교적 느립니다.  
  
-   코드에서 다음 전처리기 문을 통합하여 함수 인라인을 사용합니다.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     이 메서드를 사용 하면 일반 텍스트 루틴을 해당 MBCS 루틴에 직접 매핑할 Tchar.h에 제공 된 인라인 함수 썽크가 합니다. Tchar.h에서 코드 발췌가 수행 되는 방법의 예제를 제공 합니다.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     인라인을 사용할 수 있는 경우 형식 일치가 보장되고 추가적으로 시간이 소요되지 않으므로 최선의 방법입니다.  
  
-   코드에서 다음 전처리기 문을 통합 하 여 직접 매핑을 사용 합니다.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     기본 동작을 사용하지 않으려고 하거나 인라인을 사용할 수 없는 경우 이 방법이 가장 빠른 대안입니다. 일반 텍스트 루틴이 매크로 의해 MBCS 버전의 Tchar.h의 다음 예제와 같이 루틴에 직접 매핑해야 발생 합니다.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     이 방법을 사용 하는 경우에 문자열 인수 및 문자열 반환 값에 대 한 적절 한 데이터 형식의 사용 되도록 주의 해야 합니다. 형식 캐스팅을 사용하여 적절한 형식 일치를 보장하거나 `_TXCHAR` 일반 텍스트 데이터 형식을 사용할 수 있습니다. `_TXCHAR` 형식에 매핑되므로 **char** SBCS 코드의 형식에 매핑되므로 **unsigned char** MBCS 코드에서입니다. 일반 텍스트 매크로 대 한 자세한 내용은 참조 하세요. [일반 텍스트 매핑](../c-runtime-library/generic-text-mappings.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)