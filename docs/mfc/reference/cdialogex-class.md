---
title: "CDialogEx Class | Microsoft Docs"
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
  - "CDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogEx class"
  - "CDialogEx::PreTranslateMessage method"
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDialogEx` 클래스는 대화 상자의 배경 색과 배경 이미지를 지정합니다.  
  
## 구문  
  
```  
class CDialogEx : public CDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CDialogEx::CDialogEx](../Topic/CDialogEx::CDialogEx.md)|`CDialogEx` 개체를 생성합니다.|  
|`CDialogEx::~CDialogEx`|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CDialogEx::SetBackgroundColor](../Topic/CDialogEx::SetBackgroundColor.md)|대화 상자의 배경 색을 설정합니다.|  
|[CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)|대화 상자의 배경 이미지를 설정합니다.|  
  
## 설명  
 `CDialogEx` 클래스를 사용하려면 `CDialogEx` 클래스 대신 `CDialog` 클래스에서 대화 상자 클래스를 파생합니다.  
  
 대화 상자 이미지는 리소스 파일에 저장됩니다.  프레임워크는 리소스 파일에서 로드되는 모든 이미지를 자동으로 삭제합니다.  현재 배경 이미지를 프로그래밍 방식으로 삭제하려면 [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) 메서드를 호출하거나 `OnDestroy` 이벤트 처리기를 구현합니다.  [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) 메서드를 호출하는 경우 `HBITMAP` 매개 변수를 이미지 핸들로 제공합니다.  `CDialogEx` 개체가 이미지의 소유권을 갖게 되며 `m_bAutoDestroyBmp` 플래그가 `TRUE`이면 삭제합니다.  
  
 `CDialogEx` 개체는 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) 개체의 부모일 수 있습니다.  [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) 개체는 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) 개체가 열린 경우 `CDialogEx::SetActiveMenu` 메서드를 호출합니다.  그런 다음 `CDialogEx` 개체는 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) 개체가 닫힐 때까지 모든 메뉴 이벤트를 처리합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## 요구 사항  
 **헤더:** afxdialogex.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)