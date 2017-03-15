---
title: "콤보 상자 처리기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SETFOCUS"
  - "ON_CBN_SELENDCANCEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "콤보 상자, 처리기"
  - "ON_CBN_CLOSEUP"
  - "ON_CBN_DBLCLK"
  - "ON_CBN_DROPDOWN"
  - "ON_CBN_EDITCHANGE"
  - "ON_CBN_EDITUPDATE"
  - "ON_CBN_ERRSPACE"
  - "ON_CBN_KILLFOCUS"
  - "ON_CBN_SELCHANGE"
  - "ON_CBN_SELENDCANCEL"
  - "ON_CBN_SELENDOK"
  - "ON_CBN_SETFOCUS"
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 콤보 상자 처리기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The following map entries correspond to the function prototypes.  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|ON\_CBN\_CLOSEUP\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \)|  
|ON\_CBN\_DBLCLK\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_DROPDOWN\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_EDITCHANGE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_EDITUPDATE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_ERRSPACE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_KILLFOCUS\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELCHANGE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELENDCANCEL\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SELENDOK\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_CBN\_SETFOCUS\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)