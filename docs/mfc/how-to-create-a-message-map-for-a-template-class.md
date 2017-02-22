---
title: "방법: 템플릿 클래스에 대한 메시지 맵 만들기 | Microsoft Docs"
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
  - "메시지 맵, 템플릿 클래스"
  - "템플릿 클래스, 메시지 맵 만들기"
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 방법: 템플릿 클래스에 대한 메시지 맵 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Message mapping in MFC provides an efficient way to direct Windows messages to an appropriate C\+\+ object instance.  Examples of MFC message map targets include application classes, document and view classes, control classes, and so on.  
  
 Traditional MFC message maps are declared using the [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) macro to declare the start of the message map, a macro entry for each message\-handler class method, and finally the [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md) macro to declare the end of the message map.  
  
 One limitation with the [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) macro occurs when it is used in conjunction with a class containing template arguments.  When used with a template class, this macro will cause a compile\-time error due to the missing template parameters during macro expansion.  The [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md) macro was designed to allow classes containing a single template argument to declare their own message maps.  
  
## 예제  
 Consider an example where the MFC [CListBox](../mfc/reference/clistbox-class.md) class is extended to provide synchronization with an external data source.  The fictitious **CSyncListBox** class is declared as follows:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 The **CSyncListBox** class is templated on a single type that describes the data source it will synchronize with.  It also declares three methods that will participate in the message map of the class: **OnPaint**, **OnDestroy**, and **OnSynchronize**.  The **OnSynchronize** method is implemented as follows:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 The above implementation allows the **CSyncListBox** class to be specialized on any class type that implements the **GetCount** method, such as **CArray**, **CList**, and **CMap**.  The **StringizeElement** function is a template function prototyped by the following:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Normally, the message map for this class would be defined as:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 where **LBN\_SYNCHRONIZE** is a custom user message defined by the application, such as:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 The above macro map will not compile, due to the fact that the template specification for the **CSyncListBox** class will be missing during macro expansion.  The **BEGIN\_TEMPLATE\_MESSAGE\_MAP** macro solves this by incorporating the specified template parameter into the expanded macro map.  The message map for this class becomes:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 The following demonstrates sample usage of the **CSyncListBox** class using a **CStringList** object:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 To complete the test, the **StringizeElement** function must be specialized to work with the **CStringList** class:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/CPP/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## 참고 항목  
 [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md)   
 [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)