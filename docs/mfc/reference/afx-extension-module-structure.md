---
title: "AFX_EXTENSION_MODULE 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AFX_EXTENSION_MODULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXTENSION_MODULE 구조체"
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# AFX_EXTENSION_MODULE 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `AFX_EXTENSION_MODULE` is used during initialization of MFC extension DLLs to hold the state of extension DLL module.  
  
## 구문  
  
```  
  
      struct AFX_EXTENSION_MODULE  
{  
   BOOL bInitialized;  
   HMODULE hModule;  
   HMODULE hResource;  
   CRuntimeClass* pFirstSharedClass;  
   COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### 매개 변수  
 *bInitialized*  
 **TRUE** if the DLL module has been initialized with `AfxInitExtensionModule`.  
  
 `hModule`  
 Specifies the handle of the DLL module.  
  
 *hResource*  
 Specifies the handle of the DLL custom resource module.  
  
 *pFirstSharedClass*  
 A pointer to information \(the `CRuntimeClass` structure\) about the DLL module's first runtime class.  Used to provide the start of the runtime class list.  
  
 *pFirstSharedFactory*  
 A pointer to the DLL module's first object factory \(a `COleObjectFactory` object\).  Used to provide the start of the class factory list.  
  
## 설명  
 MFC extension DLLs need to do two things in their `DllMain` function:  
  
-   Call [AfxInitExtensionModule](../Topic/AfxInitExtensionModule.md) and check the return value.  
  
-   Create a **CDynLinkLibrary** object if the DLL will be exporting [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objects or has its own custom resources.  
  
 The `AFX_EXTENSION_MODULE` structure is used to hold a copy of the extension DLL module state, including a copy of the runtime class objects that have been initialized by the extension DLL as part of normal static object construction executed before `DllMain` is entered.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/CPP/afx-extension-module-structure_1.cpp)]  
  
 The module information stored in the `AFX_EXTENSION_MODULE` structure can be copied into the **CDynLinkLibrary** object.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/CPP/afx-extension-module-structure_2.cpp)]  
  
## 요구 사항  
 **Header:** afx.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](../Topic/AfxInitExtensionModule.md)   
 [AfxTermExtensionModule](../Topic/AfxTermExtensionModule.md)