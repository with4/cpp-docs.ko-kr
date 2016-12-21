---
title: "목록 상자 처리기 | Microsoft Docs"
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
  - "ON_LBN_DBLCLK"
  - "ON_LBN_ERRSPACE"
  - "ON_LBN_SETFOCUS"
  - "ON_LBN_SELCHANGE"
  - "ON_LBN_KILLFOCUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "목록 상자, 목록 상자 처리기"
  - "ON_LBN_DBLCLK"
  - "ON_LBN_ERRSPACE"
  - "ON_LBN_KILLFOCUS"
  - "ON_LBN_SELCHANGE"
  - "ON_LBN_SETFOCUS"
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 목록 상자 처리기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The following map entries have the corresponding function prototype.  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|ON\_LBN\_DBLCLK\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_ERRSPACE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_KILLFOCUS\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_SELCHANGE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_LBN\_SETFOCUS\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)