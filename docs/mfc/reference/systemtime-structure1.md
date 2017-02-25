---
title: "SYSTEMTIME 구조&amp;1; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SYSTEMTIME 구조체"
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# SYSTEMTIME 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`SYSTEMTIME` 구조체는 월, 일, 연도, 요일, 시간, 분, 초 및 밀리초에 대한 개별 멤버를 사용하여 날짜와 시간을 나타냅니다.  
  
## 구문  
  
```  
  
      typedef struct _SYSTEMTIME {  
   WORD wYear;  
   WORD wMonth;  
   WORD wDayOfWeek;  
   WORD wDay;  
   WORD wHour;  
   WORD wMinute;  
   WORD wSecond;  
   WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### 매개 변수  
 *wYear*  
 현재 년도입니다.  
  
 *wMonth*  
 현재 월입니다. 1월은 1입니다.  
  
 *wDayOfWeek*  
 일요일 \= 0, 월요일 1 등으로 주간의 당일입니다.  
  
 *wDay*  
 그 달의 당일입니다.  
  
 *wHour*  
 현재 시간입니다.  
  
 *wMinute*  
 현재 분입니다.  
  
 *wSecond*  
 현재 초입니다.  
  
 *wMilliseconds*  
 현재 밀리초입니다.  
  
## 예제  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/CPP/systemtime-structure1_1.cpp)]  
  
## 요구 사항  
 **헤더:** winbase.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)