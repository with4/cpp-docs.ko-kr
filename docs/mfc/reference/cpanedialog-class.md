---
title: "CPaneDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDialog class"
  - "CPaneDialog constructor"
  - "CPaneDialog::CreateObject method"
  - "CPaneDialog::OnEraseBkgnd method"
  - "CPaneDialog::OnLButtonDblClk method"
  - "CPaneDialog::OnLButtonDown method"
  - "CPaneDialog::OnUpdateCmdUI method"
  - "CPaneDialog::OnWindowPosChanging method"
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPaneDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPaneDialog` 모덜리스, 도킹 가능한 대화 상자 클래스를 지원 합니다.  
  
## 구문  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CPaneDialog::CPaneDialog`|기본 생성자입니다.|  
|`CPaneDialog::~CPaneDialog`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPaneDialog::Create](../Topic/CPaneDialog::Create.md)|도킹 가능한 대화 상자를 만들고 연결 하는 `CPaneDialog` 개체입니다.|  
|`CPaneDialog::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CPaneDialog::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CPaneDialog::HandleInitDialog](../Topic/CPaneDialog::HandleInitDialog.md)|처리는  [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) 메시지.  \(재정의 `CBasePane::HandleInitDialog`.\)|  
|`CPaneDialog::OnEraseBkgnd`|처리는  [WM\_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) 메시지.  \(재정의 [CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md).\)|  
|`CPaneDialog::OnLButtonDblClk`|처리는  [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) 메시지.  \(재정의 [CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md).\)|  
|`CPaneDialog::OnLButtonDown`|처리는  [WM\_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) 메시지.  \(재정의 [CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md).\)|  
|`CPaneDialog::OnUpdateCmdUI`|대화 상자 창을 업데이트 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/ko-kr/5dd61606-1c12-40d4-b024-f3839aa5e2e0).\)|  
|`CPaneDialog::OnWindowPosChanging`|처리는  [WM\_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) 메시지.  \(재정의 [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md).\)|  
|[CPaneDialog::SetOccDialogInfo](../Topic/CPaneDialog::SetOccDialogInfo.md)|서식 파일 대화 상자는 OLE 컨트롤 컨테이너를 지정 합니다.|  
  
## 설명  
 생성 된 `CPaneDialog` 개체에서 두 단계.  먼저 코드에서 개체를 생성 합니다.  둘째, 호출 [CPaneDialog::Create](../Topic/CPaneDialog::Create.md).  올바른 리소스 템플릿 이름이 나 서식 파일의 ID를 지정 하 고 부모 창에 포인터를 전달 해야 합니다.  그렇지 않으면 생성 프로세스가 실패합니다.  대화 상자는 WS\_CHILD 및 WS\_VISIBLE 스타일을 지정 해야 합니다.  또한 WS\_CLIPCHILDREN 및 WS\_CLIPSIBLINGS 스타일을 지정 하는 것이 좋습니다.  자세한 내용은 [창 스타일](../../mfc/reference/window-styles.md)를 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## 요구 사항  
 **헤더:** afxpanedialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [창 스타일](../../mfc/reference/window-styles.md)