---
title: "CMFCWindowsManagerDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCWindowsManagerDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCWindowsManagerDialog class"
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCWindowsManagerDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCWindowsManagerDialog` 개체는 MDI 자식 창은 MDI 응용 프로그램에서을 관리할 수 있습니다.  
  
## 구문  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](../Topic/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog.md)|`CMFCWindowsManagerDialog` 개체를 생성합니다.|  
  
## 설명  
 `CMFCWindowsManagerDialog` 응용 프로그램에서 현재 열려 있는 MDI 자식 창 목록을 포함 합니다.  사용자가이 대화 상자를 사용 하 여 MDI 자식 창의 상태를 수동으로 제어할 수 있습니다.  
  
 `CMFCWindowsManagerDialog`안에 포함 된 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md).  `CMFCWindowsManagerDialog` 수동으로 만들어야 하는 클래스가 아닙니다.  대신 함수를 호출 합니다. [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)를 만들고 표시 되 고는 `CMFCWindowsManagerDialog` 개체.  
  
## 예제  
 다음 예제에서는 생성 하는 방법을 보여 줍니다.을 `CMFCWindowsManagerDialog` 개체를 호출 하 여 `CMDIFrameWndEx::ShowWindowsDialog`.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/CPP/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## 요구 사항  
 **헤더:** afxWindowsManagerDialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)   
 [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)