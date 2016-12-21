---
title: "사용자 단추 처리기 | Microsoft Docs"
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
  - "ON_BN_HILITE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_CLICKED"
  - "ON_BN_PAINT"
  - "ON_BN_DISABLE"
  - "ON_BN_UNHILITE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_BN_CLICKED"
  - "ON_BN_DISABLE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_HILITE"
  - "ON_BN_PAINT"
  - "ON_BN_UNHILITE"
  - "사용자 단추"
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 사용자 단추 처리기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The following map entries correspond to the function prototypes.  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|ON\_BN\_CLICKED\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_DISABLE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_DOUBLECLICKED\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_HILITE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_PAINT\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_UNHILITE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)