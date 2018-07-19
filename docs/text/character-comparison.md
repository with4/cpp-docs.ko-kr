---
title: 문자 비교 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b969783a19c0836a8ab81d75820fc688df3ef31e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854953"
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