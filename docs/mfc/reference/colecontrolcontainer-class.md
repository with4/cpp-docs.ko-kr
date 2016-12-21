---
title: "COleControlContainer Class | Microsoft Docs"
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
  - "COleControlContainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤 컨테이너[C++], control site"
  - "COleControlContainer class"
  - "사용자 지정 컨트롤[MFC], sites"
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleControlContainer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤은 컨트롤 컨테이너 역할을 합니다.  
  
## 구문  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleControlContainer::COleControlContainer](../Topic/COleControlContainer::COleControlContainer.md)|`COleControlContainer` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleControlContainer::AttachControlSite](../Topic/COleControlContainer::AttachControlSite.md)|컨트롤 컨테이너에서 호스트 사이트를 만듭니다.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](../Topic/COleControlContainer::BroadcastAmbientPropertyChange.md)|앰비언트 속성이 변경 된 모든 호스트 컨트롤을 알립니다.|  
|[COleControlContainer::CheckDlgButton](../Topic/COleControlContainer::CheckDlgButton.md)|지정 된 단추 컨트롤을 수정합니다.|  
|[COleControlContainer::CheckRadioButton](../Topic/COleControlContainer::CheckRadioButton.md)|지정 된 라디오 단추 그룹을 선택합니다.|  
|[COleControlContainer::CreateControl](../Topic/COleControlContainer::CreateControl.md)|ActiveX 호스트 컨트롤을 만듭니다.|  
|[COleControlContainer::CreateOleFont](../Topic/COleControlContainer::CreateOleFont.md)|OLE 글꼴을 만듭니다.|  
|[COleControlContainer::FindItem](../Topic/COleControlContainer::FindItem.md)|지정한 컨트롤의 사용자 지정 사이트를 반환합니다.|  
|[COleControlContainer::FreezeAllEvents](../Topic/COleControlContainer::FreezeAllEvents.md)|컨트롤 사이트 이벤트를 수락 하는 경우를 결정 합니다.|  
|[COleControlContainer::GetAmbientProp](../Topic/COleControlContainer::GetAmbientProp.md)|지정 된 앰비언트 속성을 검색합니다.|  
|[COleControlContainer::GetDlgItem](../Topic/COleControlContainer::GetDlgItem.md)|지정 된 대화 상자 컨트롤을 검색합니다.|  
|[COleControlContainer::GetDlgItemInt](../Topic/COleControlContainer::GetDlgItemInt.md)|지정 된 대화 상자 컨트롤의 값을 검색합니다.|  
|[COleControlContainer::GetDlgItemText](../Topic/COleControlContainer::GetDlgItemText.md)|지정 된 대화 상자 컨트롤의 캡션을 검색합니다.|  
|[COleControlContainer::HandleSetFocus](../Topic/COleControlContainer::HandleSetFocus.md)|컨테이너 처리 하면 결정 `WM_SETFOCUS` 메시지.|  
|[COleControlContainer::HandleWindowlessMessage](../Topic/COleControlContainer::HandleWindowlessMessage.md)|창 없는 컨트롤에 보내는 메시지를 처리 합니다.|  
|[COleControlContainer::IsDlgButtonChecked](../Topic/COleControlContainer::IsDlgButtonChecked.md)|지정 된 단추의 상태를 확인합니다.|  
|[COleControlContainer::OnPaint](../Topic/COleControlContainer::OnPaint.md)|컨테이너의 일부를 다시 호출 합니다.|  
|[COleControlContainer::OnUIActivate](../Topic/COleControlContainer::OnUIActivate.md)|컨트롤에 대 한 내부에서 활성화 될 때 호출 됩니다.|  
|[COleControlContainer::OnUIDeactivate](../Topic/COleControlContainer::OnUIDeactivate.md)|컨트롤에 대 한 비활성화 되 면 호출 됩니다.|  
|[COleControlContainer::ScrollChildren](../Topic/COleControlContainer::ScrollChildren.md)|자식 창에서 스크롤 메시지를 받았을 때 프레임 워크에 의해 호출 됩니다.|  
|[COleControlContainer::SendDlgItemMessage](../Topic/COleControlContainer::SendDlgItemMessage.md)|지정 된 컨트롤에 메시지를 보냅니다.|  
|[COleControlContainer::SetDlgItemInt](../Topic/COleControlContainer::SetDlgItemInt.md)|지정 된 컨트롤의 값을 설정 합니다.|  
|[COleControlContainer::SetDlgItemText](../Topic/COleControlContainer::SetDlgItemText.md)|지정 된 컨트롤의 텍스트를 설정합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleControlContainer::m\_crBack](../Topic/COleControlContainer::m_crBack.md)|컨테이너의 배경색입니다.|  
|[COleControlContainer::m\_crFore](../Topic/COleControlContainer::m_crFore.md)|컨테이너의 전경색입니다.|  
|[COleControlContainer::m\_listSitesOrWnds](../Topic/COleControlContainer::m_listSitesOrWnds.md)|목록 컨트롤을 지원 되는 사이트입니다.|  
|[COleControlContainer::m\_nWindowlessControls](../Topic/COleControlContainer::m_nWindowlessControls.md)|호스팅된 창 없는 컨트롤의 개수입니다.|  
|[COleControlContainer::m\_pOleFont](../Topic/COleControlContainer::m_pOleFont.md)|OLE의 글꼴을 사용자 지정 컨트롤 사이트에 대 한 포인터입니다.|  
|[COleControlContainer::m\_pSiteCapture](../Topic/COleControlContainer::m_pSiteCapture.md)|캡처 제어 사이트에 대 한 포인터입니다.|  
|[COleControlContainer::m\_pSiteFocus](../Topic/COleControlContainer::m_pSiteFocus.md)|현재 입력 포커스가 있는 컨트롤에 대 한 포인터입니다.|  
|[COleControlContainer::m\_pSiteUIActive](../Topic/COleControlContainer::m_pSiteUIActive.md)|현재 위치에서 활성화 된 컨트롤에 대 한 포인터입니다.|  
|[COleControlContainer::m\_pWnd](../Topic/COleControlContainer::m_pWnd.md)|컨트롤 컨테이너를 구현 하는 창에 대 한 포인터입니다.|  
|[COleControlContainer::m\_siteMap](../Topic/COleControlContainer::m_siteMap.md)|사이트 맵입니다.|  
  
## 설명  
 ActiveX 컨트롤 사이트에 대 한 하나 이상의 지원 함으로써 이루어집니다 \(구현 `COleControlSite`\).  `COleControlContainer`완벽 하 게 구현 된  [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) 및  [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) 인터페이스에 포함 된 ActiveX 컨트롤 내부 항목으로 해당 자격 요건을 충족 하는.  
  
 일반적으로이 클래스와 함께에서 사용 `COccManager` 및 `COleControlSite` ActiveX 컨트롤에 대 한 사용자 지정 사이트를 사용자 지정 ActiveX 컨트롤 컨테이너를 구현 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## 요구 사항  
 **헤더:** afxocc.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager Class](../../mfc/reference/coccmanager-class.md)