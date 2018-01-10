---
title: "문자 비교 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28c2cd3a2e868a595d73d06b5cae8e71ec8cc313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="character-comparison"></a>문자 비교
다음 팁을 사용 합니다.  
  
-   올바르게 작동 ASCII 문자로 알려진된 선행 바이트를 비교 합니다.  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   두 개의 알 수 없는 문자를 비교 Mbstring.h에 정의 된 매크로 중 하나를 사용 하려면 필요 합니다.  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     이렇게 하면 두 바이트는 더블 바이트 문자 같은지 비교 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [버퍼 오버플로](../text/buffer-overflow.md)