---
title: 문자열에서 마지막 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88cde1d2eb30103462f7ae8f8c06274a2977fc36
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855645"
---
# <a name="last-character-in-a-string"></a>문자열의 마지막 문자
다음 팁을 사용 합니다.  
  
-   후행 바이트 범위는 ASCII 문자를 집합 대부분의 경우에서 겹칩니다. 모든 제어 문자 (32 보다 작거나)에 대 한 바이트 단위 검색을 안전 하 게 사용할 수 있습니다.  
  
-   문자열의 마지막 문자는 백슬래시 문자 있는지를 확인할 수 있습니다는 코드의 다음 줄을 고려 합니다.  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     때문에 `strlen` MBCS 인식 하지 않는 멀티 바이트 문자열의 문자 수가 바이트 수를 반환 합니다. 또한, 이때 일부 코드 페이지 (예:: 932), '\\' (0x5c)는 유효한 후행 바이트 (`sz` 는 C 문자열)입니다.  
  
     이러한 방식으로 코드를 다시 작성 한 가지 가능한 해결책이입니다.  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     이 코드는 MBCS 함수를 사용 하 여 `_mbsrchr` 및 `_mbsinc`합니다. 이러한 함수에서 MBCS 인식 되므로 구별할 수 있습니다는 '\\'문자에는 후행 바이트와 '\\'. 코드는 문자열의 마지막 문자 ('\0') null 인 경우 특별 한 조치를 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [문자 할당](../text/character-assignment.md)