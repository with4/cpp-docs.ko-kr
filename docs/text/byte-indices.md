---
title: 바이트 인덱스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 509e66c7ea458519eaa9dc4f52c8a6b65c789d0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863802"
---
# <a name="byte-indices"></a>바이트 인덱스
다음 팁을 사용 합니다.  
  
-   포인터 조작으로 인 한 것과 유사한 문제를 표시 하는 문자열로 바이트 단위는 인덱스를 사용 합니다. 백슬래시 문자에 대 한 문자열을 검색 하는이 예를 살펴보십시오.  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     후행 바이트를 선행 바이트가 아니라 인덱스할 수 및 있으므로를 가리키지 수는 `character`합니다.  
  
-   사용 하 여 [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) 앞의 문제를 해결 하는 함수:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     이 되므로 선행 바이트에 올바로 인덱스에 `character`합니다. `_mbclen` 함수는 문자 (1 개 또는 2 바이트)의 크기를 결정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [문자열의 마지막 문자](../text/last-character-in-a-string.md)