---
title: "TCHAR를 사용합니다. 데이터 형식 사용 H | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tchar.h
- TCHAR
dev_langs: C++
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28255b2e47c48b89b0bd6aea044fe0c15c1f2a08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS 코드와 TCHAR.H 데이터 형식 사용
때 매니페스트 상수 **_MBCS** 은 지정 된 제네릭 텍스트 루틴 정의 루틴의 다음 유형 중 하나에 매핑됩니다.  
  
-   멀티바이트 바이트, 문자 및 문자열을 적절하게 처리하는 SBCS 루틴. 문자열 인수 형식으로 예상 되는 경우 **char\***합니다. 예를 들어 `_tprintf` 매핑됩니다 `printf`;에 대 한 문자열 인수 `printf` 형식의 **char\***합니다. 사용 하는 경우는 **_TCHAR** 문자열에 대 한 일반 텍스트 데이터 형식을 형식, 형식 및 실제 매개 변수 형식에 대 한 `printf` 때문에 일치 **_TCHAR** \* 매핑됩니다 **char \***.  
  
-   MBCS 관련 루틴. 문자열 인수 형식으로 예상 되는 경우 `unsigned` **char\***합니다. 예를 들어 `_tcsrev` 매핑됩니다 `_mbsrev`필요한 형식의 문자열을 반환 하는 `unsigned` **char\***합니다. 사용 하는 경우는 **_TCHAR** 문자열 형식에 대 한 일반 텍스트 데이터 형식 충돌이 발생 하는 잠재적인 형식 때문에 **_TCHAR** 입력 맵을 `char`합니다.  
  
 이러한 형식 충돌(및 이로 인한 C 컴파일러 경고 또는 C++ 컴파일러 오류)을 방지하기 위한 방법으로는 다음 세 가지가 있습니다.  
  
-   기본 동작을 사용합니다. Tchar.h와 다음 예제와 같이 런타임 라이브러리 루틴에에서 제네릭 텍스트 루틴 프로토타입을 제공합니다.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     프로토타입에 대 기본적인 경우 `_tcsrev` 매핑됩니다 `_mbsrev` Libc.lib에 썽크를 통해. 이 변경의 종류는 `_mbsrev` 매개 변수 들어오고 나가는 값을 반환할 **_TCHAR \***  (즉, `char`  **\*** )를 `unsigned` `char` **\***. 이 방법을 사용 하는 경우 형식은 일치를 사용 하면 **_TCHAR**, 함수 호출 오버 헤드로 인해 상대적으로 속도가 느립니다.  
  
-   코드에서 다음 전처리기 문을 통합하여 함수 인라인을 사용합니다.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     이 방법을 사용 하면 인라인 함수 썽크가, Tchar.h의 제네릭 텍스트 루틴 해당 MBCS 루틴에 직접 매핑할 수 제공 합니다. Tchar.h에서 다음 코드 발췌 한이 수행 되는 방법의 예를 제공 합니다.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     인라인을 사용할 수 있는 경우 형식 일치가 보장되고 추가적으로 시간이 소요되지 않으므로 최선의 방법입니다.  
  
-   코드에서 다음 전처리기 문은 통합 하 여 직접 매핑을 사용 합니다.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     기본 동작을 사용하지 않으려고 하거나 인라인을 사용할 수 없는 경우 이 방법이 가장 빠른 대안입니다. 제네릭 텍스트 루틴 MBCS 버전 Tchar.h에서 다음 예제와 같이 루틴의 변수에 직접 매크로로 매핑할 수에 발생 합니다.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     이 방법을 사용 하는 경우에 문자열 인수 및 반환 값 문자열에 대 한 적절 한 데이터 형식의 사용을 보장 하려면 주의 해야 합니다. 형식 캐스팅을 사용 하 여 형식이 일치 하거나 사용할 수 있습니다는 **_TXCHAR** 일반 텍스트 데이터 형식입니다. **_TXCHAR** 입력 하는 지도 `char` SBCS 코드를 입력 하는 지도에 `unsigned` `char` MBCS 코드에 있습니다. 제네릭 텍스트 매크로 대 한 자세한 내용은 참조 [제네릭 텍스트 매핑](../c-runtime-library/generic-text-mappings.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)