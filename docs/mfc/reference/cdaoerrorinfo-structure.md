---
title: "CDaoErrorInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoErrorInfo 구조체"
  - "DAO(Data Access Objects), 오류 컬렉션"
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoErrorInfo 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `CDaoErrorInfo` structure contains information about an error object defined for data access objects \(DAO\).  
  
## 구문  
  
```  
  
      struct CDaoErrorInfo  
{  
   long m_lErrorCode;  
   CString m_strSource;  
   CString m_strDescription;  
   CString m_strHelpFile;  
   long m_lHelpContext;  
};  
```  
  
#### 매개 변수  
 *m\_lErrorCode*  
 A numeric DAO error code.  See the topic "Trappable Data Access Errors" in DAO Help.  
  
 *m\_strSource*  
 The name of the object or application that originally generated the error.  The Source property specifies a string expression representing the object that originally generated the error; the expression is usually the object's class name.  For details, see the topic "Source Property" in DAO Help.  
  
 *m\_strDescription*  
 A descriptive string associated with an error.  For details, see the topic "Description Property" in DAO Help.  
  
 *m\_strHelpFile*  
 A fully qualified path to a Microsoft Windows Help file.  For details, see the topic "HelpContext, HelpFile Properties" in DAO Help.  
  
 *m\_lHelpContext*  
 A context ID for a topic in a Microsoft Windows Help file.  For details, see the topic "HelpContext, HelpFile Properties" in DAO Help.  
  
## 설명  
 MFC does not encapsulate DAO error objects in a class.  Instead, the [CDaoException](../../mfc/reference/cdaoexception-class.md) class supplies an interface for accessing the Errors collection contained in the DAO **DBEngine** object, the object that also contains all workspaces.  When an MFC DAO operation throws a `CDaoException` object that you catch, MFC fills a `CDaoErrorInfo` structure and stores it in the exception object's [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) member. \(If you choose to call DAO directly, you must call the exception object's [GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) member function yourself to fill `m_pErrorInfo`.\)  
  
 For more information about handling DAO errors, see the article [Exceptions: Database Exceptions](../../mfc/exceptions-database-exceptions.md).  For related information, see the topic "Error Object" in DAO Help.  
  
 Information retrieved by the [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) member function is stored in a `CDaoErrorInfo` structure.  Examine the [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) data member from a `CDaoException` object that you catch in an exception handler, or call `GetErrorInfo` from a `CDaoException` object that you create explicitly in order to check errors that might have occurred during a direct call to the DAO interfaces.  `CDaoErrorInfo` also defines a `Dump` member function in debug builds.  You can use `Dump` to dump the contents of a `CDaoErrorInfo` object.  
  
## 요구 사항  
 **Header:** afxdao.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)