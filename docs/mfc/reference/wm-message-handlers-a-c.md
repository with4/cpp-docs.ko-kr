---
title: "WM_ 메시지 처리기: A - C | Microsoft Docs"
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
  - "ON_WM_CREATE"
  - "ON_WM_COMPACTING"
  - "ON_WM_CHARTOITEM"
  - "ON_WM_ASKCBFORMATNAME"
  - "ON_WM_CTLCOLOR"
  - "ON_WM_COMPAREITEM"
  - "ON_WM_CHILDACTIVATE"
  - "ON_WM_CONTEXTMENU"
  - "ON_WM_ACTIVATE"
  - "ON_WM_CANCELMODE"
  - "ON_WM_CLOSE"
  - "ON_WM_CAPTURECHANGED"
  - "ON_WM_ACTIVATEAPP"
  - "ON_WM_CHAR"
  - "ON_WM_CHANGECBCHAIN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_ACTIVATE"
  - "ON_WM_ACTIVATEAPP"
  - "ON_WM_ASKCBFORMATNAME"
  - "ON_WM_CANCELMODE"
  - "ON_WM_CAPTURECHANGED"
  - "ON_WM_CHANGECBCHAIN"
  - "ON_WM_CHAR"
  - "ON_WM_CHARTOITEM"
  - "ON_WM_CHILDACTIVATE"
  - "ON_WM_CLOSE"
  - "ON_WM_COMPACTING"
  - "ON_WM_COMPAREITEM"
  - "ON_WM_CONTEXTMENU"
  - "ON_WM_CREATE"
  - "ON_WM_CTLCOLOR"
  - "WM_ 메시지"
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
caps.latest.revision: 16
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WM_ 메시지 처리기: A - C
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The following map entries on the left correspond to the function prototypes on the right:  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|ON\_WM\_ACTIVATE\(\)|afx\_msg void [OnActivate](../Topic/CWnd::OnActivate.md)\(UINT, CWnd\*, BOOL\);|  
|ON\_WM\_ACTIVATEAPP\(\)|afx\_msg void [OnActivateApp](../Topic/CWnd::OnActivateApp.md)\(BOOL, DWORD\);|  
|ON\_WM\_APPCOMMAND\(\)|afx\_msg void [OnAppCommand](../Topic/CWnd::OnAppCommand.md)\(CWnd\*, UINT, UINT, UINT\);|  
|ON\_WM\_ASKCBFORMATNAME\(\)|afx\_msg void [OnAskCbFormatName](../Topic/CWnd::OnAskCbFormatName.md)\(UINT, LPSTR\);|  
|ON\_WM\_CANCELMODE\(\)|afx\_msg void [OnCancelMode](../Topic/CWnd::OnCancelMode.md)\(\);|  
|ON\_WM\_CAPTURECHANGED\(\)|afx\_msg void [OnCaptureChanged](../Topic/CWnd::OnCaptureChanged.md)\(CWnd\*\);|  
|ON\_WM\_CHANGECBCHAIN\(\)|afx\_msg void [OnChangeCbChain](../Topic/CWnd::OnChangeCbChain.md)\(HWND, HWND\);|  
|ON\_WM\_CHAR\(\)|afx\_msg void [OnChar](../Topic/CWnd::OnChar.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_CHARTOITEM\(\)|afx\_msg int [OnCharToItem](../Topic/CWnd::OnCharToItem.md)\(UINT, CWnd\*, UINT\);|  
|ON\_WM\_CHILDACTIVATE\(\)|afx\_msg void [OnChildActivate](../Topic/CWnd::OnChildActivate.md)\(\);|  
|ON\_WM\_CLIPBOARDUPDATE\(\)|afx\_msg void [OnClipboardUpdate](../Topic/CWnd::OnClipboardUpdate.md)\(\);|  
|ON\_WM\_CLOSE\(\)|afx\_msg void [OnClose](../Topic/CWnd::OnClose.md)\(\);|  
|ON\_WM\_COMPACTING\(\)|afx\_msg void [OnCompacting](../Topic/CWnd::OnCompacting.md)\(UINT\);|  
|ON\_WM\_COMPAREITEM\(\)|afx\_msg int [OnCompareItem](../Topic/CWnd::OnCompareItem.md)\(LPCOMPAREITEMSTRUCT\);|  
|ON\_WM\_CONTEXTMENU\(\)|afx\_msg void [OnContextMenu](../Topic/CWnd::OnContextMenu.md)\(CWnd\*, CPoint\);|  
|ON\_WM\_COPYDATA\(\)|afx\_msg BOOL [OnCopyData](../Topic/CWnd::OnCopyData.md)\(CWnd\* pWnd, COPYDATASTRUCT\* pCopyDataStruct\);|  
|ON\_WM\_CREATE\(\)|afx\_msg int [OnCreate](../Topic/CWnd::OnCreate.md)\(LPCREATESTRUCT\);|  
|ON\_WM\_CTLCOLOR\(\)|afx\_msg HBRUSH [OnCtlColor](../Topic/CWnd::OnCtlColor.md)\(CDC\*, CWnd\*, UINT\);|  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)   
 [WM\_ 메시지 처리기](../../mfc/reference/handlers-for-wm-messages.md)