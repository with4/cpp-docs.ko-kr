---
title: "CDaoWorkspaceInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoWorkspaceInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspaceInfo 구조체"
  - "DAO(Data Access Objects), 작업 영역 컬렉션"
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoWorkspaceInfo 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `CDaoWorkspaceInfo` structure contains information about a workspace defined for data access objects \(DAO\) database access.  
  
## 구문  
  
```  
  
      struct CDaoWorkspaceInfo  
{  
   CString m_strName;           // Primary  
   CString m_strUserName;       // Secondary  
   BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### 매개 변수  
 `m_strName`  
 Uniquely names the workspace object.  To retrieve the value of this property directly, call the querydef object's [GetName](../Topic/CDaoQueryDef::GetName.md) member function.  For more information, see the topic "Name Property" in DAO Help.  
  
 *m\_strUserName*  
 A value that represents the owner of a workspace object.  For related information, see the topic "UserName Property" in DAO Help.  
  
 *m\_bIsolateODBCTrans*  
 A value that indicates whether multiple transactions that involve the same ODBC database are isolated.  For more information, see [CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md).  For related information, see the topic "IsolateODBCTrans Property" in DAO Help.  
  
## 설명  
 The workspace is an object of class [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md).  The references to Primary, Secondary, and All above indicate how the information is returned by the [GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md) member function in class `CDaoWorkspace`.  
  
 Information retrieved by the [CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md) member function is stored in a `CDaoWorkspaceInfo` structure.  `CDaoWorkspaceInfo` also defines a `Dump` member function in debug builds.  You can use `Dump` to dump the contents of a `CDaoWorkspaceInfo` object.  
  
## 요구 사항  
 **Header:** afxdao.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)