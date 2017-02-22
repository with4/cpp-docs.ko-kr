---
title: "수명 및 표시 영역 요약 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "수명, 표시 유형"
  - "표시 여부, 식별자"
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 수명 및 표시 영역 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 표에서는 대부분의 식별자에 대한 수명 및 표시 유형 특징을 요약합니다.  처음 세 열에서는 수명과 표시 유형을 정의하는 특성을 제공합니다.  처음 세 열에서 제공하는 특성이 있는 식별자의 수명과 표시 유형은 4번째 열과 5번째 열에 표시되어 있습니다.  가능한 모든 경우가 이 표에 포함되어 있지는 않습니다.  자세한 내용은 [저장소 클래스](../c-language/c-storage-classes.md)를 참조하십시오.  
  
### 수명 및 표시 유형에 대한 요약  
  
|특성:<br /><br /> 수준|항목|저장소 클래스<br /><br /> 지정자|결과:<br /><br /> 수명|표시 유형|  
|----------------|--------|---------------------|----------------|-----------|  
|파일 범위|변수 정의|**static**|전역|이 항목이 발생하는 소스 파일의 나머지 부분|  
||변수 선언|`extern`|전역|이 항목이 발생하는 소스 파일의 나머지 부분|  
||함수 프로토타입 또는 정의|**static**|전역|단일 소스 파일|  
||함수 프로토타입|`extern`|전역|소스 파일의 나머지 부분|  
|블록 범위|변수 선언|`extern`|전역|블록|  
||변수 정의|**static**|전역|블록|  
||변수 정의|**auto** 또는 **register**|지역|블록|  
  
## 예제  
  
### 설명  
 다음 예제에서는 변수의 블록, 중첩 및 표시 유형을 보여 줍니다.  
  
### 코드  
  
```  
// Lifetime_and_Visibility.c  
  
#include <stdio.h>  
  
int i = 1;  // i defined at external level  
  
int main()  // main function defined at external level  
{  
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)  
    {                                 // Begin first nested block  
        int i = 2, j = 3;          // i and j defined at internal level  
        printf_s( "%d %d\n", i, j );  // Prints 2, 3  
        {                             // Begin second nested block  
            int i = 0;                // i is redefined  
            printf_s( "%d %d\n", i, j ); // Prints 0, 3  
        }                             // End of second nested block  
        printf_s( "%d\n", i );        // Prints 2 (outer definition  
                                      //  restored)  
    }                                 // End of first nested block  
    printf_s( "%d\n", i );            // Prints 1 (external level  
                                      // definition restored)  
    return 0;  
}   
```  
  
### 설명  
 이 예제에는 네 가지 수준의 표시 유형\(외부 수준과 세 가지 블록 수준\)이 있습니다.  값은 각 문 다음에 있는 주석에 언급된 것처럼 화면에 출력됩니다.  
  
## 참고 항목  
 [수명, 범위, 표시 영역 및 링크](../c-language/lifetime-scope-visibility-and-linkage.md)