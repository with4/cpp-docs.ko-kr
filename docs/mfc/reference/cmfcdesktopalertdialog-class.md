---
title: "CMFCDesktopAlertDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertDialog class"
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCDesktopAlertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDesktopAlertDialog` 클래스는 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)와 함께 사용하여 팝업 창에 사용자 지정 대화 상자를 표시합니다.  
  
## 구문  
  
```  
class CMFCDesktopAlertDialog : public CDialogEx  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCDesktopAlertDialog::CreateFromParams](../Topic/CMFCDesktopAlertDialog::CreateFromParams.md)||  
|[CMFCDesktopAlertDialog::GetDlgSize](../Topic/CMFCDesktopAlertDialog::GetDlgSize.md)||  
|[CMFCDesktopAlertDialog::HasFocus](../Topic/CMFCDesktopAlertDialog::HasFocus.md)||  
|[CMFCDesktopAlertDialog::PreTranslateMessage](../Topic/CMFCDesktopAlertDialog::PreTranslateMessage.md)|\(`CDialogEx::PreTranslateMessage`를 재정의합니다.\)|  
  
### 설명  
 다음 단계를 수행하여 팝업 창에 사용자 지정 대화 상자를 표시합니다.  
  
1.  `CMFCDesktopAlertDialog`에서 클래스를 파생합니다.  
  
2.  프로젝트 리소스에서 자식 대화 상자 템플릿을 만듭니다.  
  
3.  대화 상자 템플릿의 리소스 ID 및 매개 변수로 파생 클래스의 런타임 클래스 정보에 대한 포인터를 사용하여 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)를 호출합니다.  
  
4.  호스트된 컨트롤에서 생성되는 모든 알림을 처리하는 사용자 지정 대화 상자를 프로그래밍하거나 이러한 알림을 직접 처리하는 호스트된 컨트롤을 프로그래밍합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)  
  
## 요구 사항  
 **헤더:** afxDesktopAlertDialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWndInfo Class](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CDialogEx Class](../../mfc/reference/cdialogex-class.md)