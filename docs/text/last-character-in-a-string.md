---
title: "문자열의 마지막 문자 | Microsoft Docs"
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
  - "문자열의 마지막 문자"
  - "MBCS[C++], 문자열의 마지막 문자"
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# 문자열의 마지막 문자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 팁을 사용하십시오.  
  
-   대부분의 경우 후행 바이트 범위는 ASCII 문자 집합과 겹칩니다.  32자 미만의 모든 컨트롤 문자에 대해 안전하게 바이트 단위 검색을 사용할 수 있습니다.  
  
-   다음 코드를 보면 문자열의 마지막 문자가 백슬래시 문자인지를 확인할 수 있습니다.  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     `strlen`은 MBCS를 인식하지 않으므로 멀티바이트 문자열에서 문자 수가 아니라 바이트 수를 반환합니다.  또한 일부 코드 페이지\(예: 932\)에서 '\\'\(0x5c\)는 유효한 후행 바이트입니다. 여기서 `sz`는 C 문자열입니다.  
  
     한 가지 가능한 방법은 다음과 같이 코드를 다시 작성하는 것입니다.  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     위 코드는 MBCS 함수인 `_mbsrchr`와 `_mbsinc`를 사용합니다.  이들 함수는 MBCS를 인식하기 때문에 '\\' 문자와 후행 바이트 '\\'를 구별할 수 있습니다.  이 코드는 문자열의 마지막 문자가 Null\('\\0'\)인 경우에 동작을 수행합니다.  
  
## 참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [문자 할당](../text/character-assignment.md)