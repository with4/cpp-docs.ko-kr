---
title: "문자 비교 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문자[C++], 비교"
  - "문자 비교"
  - "MBCS[C++], 문자 비교"
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# 문자 비교
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 팁을 사용하십시오.  
  
-   알려진 선행 바이트와 ASCII 문자 비교는 제대로 수행됩니다.  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   두 개의 알 수 없는 문자를 비교하려면 Mbstring.h에 정의된 매크로 중 하나를 사용해야 합니다.  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     이렇게 하면 더블바이트 문자의 바이트 두 개가 모두 비교됩니다.  
  
## 참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [버퍼 오버플로](../text/buffer-overflow.md)