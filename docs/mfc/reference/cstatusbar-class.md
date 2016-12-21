---
title: "CStatusBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBar class"
  - "indicators"
  - "indicators, status bar"
  - "상태 표시줄"
  - "status indicators"
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤 막대에 텍스트 출력 창 행 "표시기"  
  
## 구문  
  
```  
class CStatusBar : public CControlBar  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CStatusBar::CStatusBar](../Topic/CStatusBar::CStatusBar.md)|`CStatusBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStatusBar::CommandToIndex](../Topic/CStatusBar::CommandToIndex.md)|지정 된 표시기 ID에 대 한 인덱스를 가져옵니다.|  
|[CStatusBar::Create](../Topic/CStatusBar::Create.md)|상태 표시줄 생성, 연결에 `CStatusBar` 개체와 초기 막대와 글꼴 높이 설정 합니다.|  
|[CStatusBar::CreateEx](../Topic/CStatusBar::CreateEx.md)|생성 한 `CStatusBar` 개체에 포함 된 추가 스타일 `CStatusBarCtrl` 개체.|  
|[CStatusBar::DrawItem](../Topic/CStatusBar::DrawItem.md)|시각적 측면이 소유자 그리기 상태 표시줄 컨트롤이 변경 되 면 호출 됩니다.|  
|[CStatusBar::GetItemID](../Topic/CStatusBar::GetItemID.md)|지표 ID의 지정 된 인덱스를 가져옵니다.|  
|[CStatusBar::GetItemRect](../Topic/CStatusBar::GetItemRect.md)|가져옵니다 인덱스가 지정 된 사각형을 표시합니다.|  
|[CStatusBar::GetPaneInfo](../Topic/CStatusBar::GetPaneInfo.md)|지표 ID, 스타일 및 너비의 지정 된 인덱스를 가져옵니다.|  
|[CStatusBar::GetPaneStyle](../Topic/CStatusBar::GetPaneStyle.md)|표시기 스타일을 지정 된 인덱스를 가져옵니다.|  
|[CStatusBar::GetPaneText](../Topic/CStatusBar::GetPaneText.md)|텍스트를 표시기의 지정 된 인덱스를 가져옵니다.|  
|[CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md)|내부 공용 컨트롤에 직접 액세스할 수 있습니다.|  
|[CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)|지표 Id를 설정합니다.|  
|[CStatusBar::SetPaneInfo](../Topic/CStatusBar::SetPaneInfo.md)|지표 ID, 스타일, 너비를 지정 된 인덱스에 대 한 설정입니다.|  
|[CStatusBar::SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md)|주어진된 인덱스 표시기 스타일을 설정입니다.|  
|[CStatusBar::SetPaneText](../Topic/CStatusBar::SetPaneText.md)|주어진된 인덱스에 대 한 표시기가 텍스트를 설정합니다.|  
  
## 설명  
 출력 창은 일반적으로 메시지 줄 및 상태 표시기로 사용 됩니다.  선택한 메뉴 명령을 간략하게 설명 하는 메뉴 도움말 메시지 줄과 SCROLL LOCK, NUM LOCK 및 기타 키의 상태를 표시 하는 표시기 등이 있습니다.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), 멤버 함수는 새 MFC 4.0에 상태 표시줄을 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다.  `CStatusBar`멤버 함수 대부분의 공용 Windows 컨트롤의 기능을 지정합니다. 그러나 호출 하면 `GetStatusBarCtrl`, 상태 표시줄에 Windows 95\/98 상태 표시줄의 특성을 더 많이 제공할 수 있습니다.  호출 하면 `GetStatusBarCtrl`에 대 한 참조를 반환 합니다는 `CStatusBarCtrl` 개체.  참조  [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Windows 공용 컨트롤을 사용 하 여 도구 모음을 디자인 하는 방법에 대 한 자세한 내용은.  공용 컨트롤에 대 한 자세한 내용은  [공용 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775493) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 프레임 워크에서 배열 위치 0에 가장 왼쪽에 있는 표시기를 표시기 정보를 저장합니다.  상태 표시줄을 만들 때 해당 표시기를 프레임 워크를 연결 하는 Id 문자열의 배열을 사용 합니다.  다음은 문자열 ID 또는 인덱스 표시기에 액세스할 수 있습니다.  
  
 기본적으로 첫 번째 표시기 "탄력"입니다: 다른 창 오른쪽 맞춤 수 있도록 다른 표시기 창으로 미사용 상태 표시줄 길이를 사용 합니다.  
  
 상태 표시줄을 만들려면 다음과이 같이 하십시오.  
  
1.  생성 된 `CStatusBar` 개체입니다.  
  
2.  호출 된  [만들기](../Topic/CStatusBar::Create.md) \(또는  [CreateEx](../Topic/CStatusBar::CreateEx.md)\) 상태 표시줄 창에 연결 하는 함수는 `CStatusBar` 개체.  
  
3.  호출  [SetIndicators](../Topic/CStatusBar::SetIndicators.md) 문자열 ID 각 표시기와 연결 합니다.  
  
 텍스트 상태 표시줄 창에서 업데이트에 다음 세 가지가 있습니다.  
  
1.  호출  [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md) 텍스트 창 0만 업데이트 합니다.  
  
2.  호출  [CCmdUI::SetText](../Topic/CCmdUI::SetText.md) 에 있는 상태 표시줄의 `ON_UPDATE_COMMAND_UI` 처리기.  
  
3.  호출  [SetPaneText](../Topic/CStatusBar::SetPaneText.md) 모든 창에 대 한 텍스트를 업데이트 합니다.  
  
 호출  [SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md) 스타일 창의 상태 표시줄을 업데이트 합니다.  
  
 사용에 대 한 자세한 내용은 `CStatusBar`, 문서를 참조 하십시오.  [mfc에서 상태 표시줄 구현](../../mfc/status-bar-implementation-in-mfc.md) 및  [기술 참고 31: 컨트롤 막대](../../mfc/tn031-control-bars.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [CTRLBARS MFC 샘플](../../top/visual-cpp-samples.md)   
 [MFC 샘플 DLGCBR32](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)   
 [CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)