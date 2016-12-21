---
title: "내보낸 DLL 함수 시작 지점 | Microsoft Docs"
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
  - "DLL 내보내기, 함수"
  - "MFC, 상태 데이터 관리"
  - "상태 관리, 내보낸 DLL"
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 내보낸 DLL 함수 시작 지점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

For exported functions of a DLL, use the [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) macro to maintain the proper global state when switching from the DLL module to the calling application's DLL.  
  
 When called, this macro sets `pModuleState`, a pointer to an `AFX_MODULE_STATE` structure containing global data for the module, as the effective module state for the remainder of the containing scope of the function.  Upon leaving the scope containing the macro, the previous effective module state is automatically restored.  
  
 This switching is achieved by constructing an instance of an **AFX\_MODULE\_STATE** class on the stack.  In its constructor, this class obtains a pointer to the current module state and stores it in a member variable, and then sets `pModuleState` as the new effective module state.  In its destructor, this class restores the pointer stored in its member variable as the effective module state.  
  
 If you have an exported function, such as one that launches a dialog box in your DLL, you need to add the following code to the beginning of the function:  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/CPP/exported-dll-function-entry-points_1.cpp)]  
  
 This swaps the current module state with the state returned from [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) until the end of the current scope.  
  
 Problems with resources in DLLs will occur if the `AFX_MANAGE_STATE` macro is not used.  By default, MFC uses the resource handle of the main application to load the resource template.  This template is actually stored in the DLL.  The root cause is that MFC's module state information has not been switched by the `AFX_MANAGE_STATE` macro.  The resource handle is recovered from MFC's module state.  Not switching the module state causes the wrong resource handle to be used.  
  
 `AFX_MANAGE_STATE` does not need to be put into every function in the DLL.  For example, `InitInstance` can be called by the MFC code in the application without `AFX_MANAGE_STATE` because MFC automatically shifts the module state before `InitInstance` and then switches it back after `InitInstance` returns.  The same is true for all message\-map handlers.  Regular DLLs actually have a special master window procedure that automatically switches the module state before routing any message.  
  
## 참고 항목  
 [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)