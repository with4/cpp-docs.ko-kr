---
title: "COM 인터페이스 진입점 | Microsoft Docs"
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
  - "COM 인터페이스, 진입점"
  - "진입점, COM 인터페이스"
  - "MFC COM, COM 인터페이스 진입점"
  - "MFC, 상태 데이터 관리"
  - "OLE, 인터페이스 진입점"
  - "상태 관리, OLE/COM 인터페이스"
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM 인터페이스 진입점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

For member functions of a COM interface, use the [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md) macro to maintain the proper global state when calling methods of an exported interface.  
  
 Typically, member functions of interfaces implemented by `CCmdTarget`\-derived objects already use this macro to provide automatic initialization of the `pThis` pointer.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/CPP/com-interface-entry-points_1.cpp)]  
  
 For additional information, see [Technical Note 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) on MFC\/OLE **IUnknown** implementation.  
  
 The `METHOD_PROLOGUE` macro is defined as:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 The portion of the macro concerned with managing the global state is:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 In this expression, *m\_pModuleState* is assumed to be a member variable of the containing object.  It is implemented by the `CCmdTarget` base class and is initialized to the appropriate value by `COleObjectFactory`, when the object is instantiated.  
  
## 참고 항목  
 [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)