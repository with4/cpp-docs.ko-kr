---
title: "CToolTipCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl class"
  - "data tips [C++]"
  - "도구 설명[C++], tool tip controls"
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"도구 설명 컨트롤의" 도구 상자에서 응용 프로그램의 용도 설명 하는 텍스트 한 줄을 표시 하는 작은 팝업 창 기능을 캡슐화 합니다.  
  
## 구문  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CToolTipCtrl::CToolTipCtrl](../Topic/CToolTipCtrl::CToolTipCtrl.md)|`CToolTipCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CToolTipCtrl::Activate](../Topic/CToolTipCtrl::Activate.md)|활성화 하 고 도구 설명 컨트롤을 비활성화 합니다.|  
|[CToolTipCtrl::AddTool](../Topic/CToolTipCtrl::AddTool.md)|도구 설명 컨트롤에 도구를 등록합니다.|  
|[CToolTipCtrl::AdjustRect](../Topic/CToolTipCtrl::AdjustRect.md)|Tool tip 컨트롤이 텍스트 사이의 변환 사각형 및 해당 창의 사각형을 표시합니다.|  
|[CToolTipCtrl::Create](../Topic/CToolTipCtrl::Create.md)|도구 설명 컨트롤을 만들고이에 연결 된 `CToolTipCtrl` 개체입니다.|  
|[CToolTipCtrl::CreateEx](../Topic/CToolTipCtrl::CreateEx.md)|Tool tip 컨트롤이 지정 된 Windows 확장된 스타일 만들고 연결 하는 `CToolTipCtrl` 개체입니다.|  
|[CToolTipCtrl::DelTool](../Topic/CToolTipCtrl::DelTool.md)|도구 설명 컨트롤에서 도구를 제거합니다.|  
|[CToolTipCtrl::GetBubbleSize](../Topic/CToolTipCtrl::GetBubbleSize.md)|도구 설명의 크기를 검색합니다.|  
|[CToolTipCtrl::GetCurrentTool](../Topic/CToolTipCtrl::GetCurrentTool.md)|크기, 위치 및 현재 도구 설명 컨트롤에 표시 되는 도구 설명 창의 텍스트 등의 정보를 검색 합니다.|  
|[CToolTipCtrl::GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md)|초기, 팝업 및 reshow 검색 도구에 대 한 현재 설정 된 기간에 컨트롤 팁.|  
|[CToolTipCtrl::GetMargin](../Topic/CToolTipCtrl::GetMargin.md)|위쪽, 왼쪽, 아래쪽 및 오른쪽 여백을 설정에 대 한 도구 설명 창을 검색 합니다.|  
|[CToolTipCtrl::GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md)|도구 설명 창의 최대 너비를 검색합니다.|  
|[CToolTipCtrl::GetText](../Topic/CToolTipCtrl::GetText.md)|도구 설명 컨트롤에 도구를 유지 하는 텍스트를 검색 합니다.|  
|[CToolTipCtrl::GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md)|도구 팁 창에서 배경 색을 검색합니다.|  
|[CToolTipCtrl::GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md)|도구 설명 창의 텍스트 색을 검색합니다.|  
|[CToolTipCtrl::GetTitle](../Topic/CToolTipCtrl::GetTitle.md)|현재 도구 설명 컨트롤의 제목을 검색합니다.|  
|[CToolTipCtrl::GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md)|관리 도구 설명 컨트롤이 도구 개수를 검색 합니다.|  
|[CToolTipCtrl::GetToolInfo](../Topic/CToolTipCtrl::GetToolInfo.md)|도구 설명 컨트롤을 유지 하는 도구에 대 한 정보를 검색 합니다.|  
|[CToolTipCtrl::HitTest](../Topic/CToolTipCtrl::HitTest.md)|점을 지정 된 도구의 경계 직사각형 내에 있는지 테스트 합니다.  그렇다면이 도구에 대 한 정보를 검색 합니다.|  
|[CToolTipCtrl::Pop](../Topic/CToolTipCtrl::Pop.md)|표시 된 도구 설명 창을 보기에서 제거합니다.|  
|[CToolTipCtrl::Popup](../Topic/CToolTipCtrl::Popup.md)|현재 도구 설명 컨트롤을 마지막 마우스 메시지의 좌표에 표시 됩니다.|  
|[CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md)|마우스 메시지 처리를 도구 설명 컨트롤에 전달합니다.|  
|[CToolTipCtrl::SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md)|팝업에서 초기 설정 및 reshow 도구 설명 컨트롤에 대 한 기간입니다.|  
|[CToolTipCtrl::SetMargin](../Topic/CToolTipCtrl::SetMargin.md)|위쪽, 왼쪽, 아래쪽 및 오른쪽 여백에 대 한 도구 설명 창 설정합니다.|  
|[CToolTipCtrl::SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md)|도구 설명 창의 최대 너비를 설정합니다.|  
|[CToolTipCtrl::SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md)|도구 팁 창에서 배경 색을 설정 합니다.|  
|[CToolTipCtrl::SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md)|도구 팁 창에서 텍스트 색을 설정합니다.|  
|[CToolTipCtrl::SetTitle](../Topic/CToolTipCtrl::SetTitle.md)|표준 아이콘 및 제목 문자열에 도구 설명이 추가 됩니다.|  
|[CToolTipCtrl::SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md)|도구 설명 도구를 유지 관리 하는 정보를 설정 합니다.|  
|[CToolTipCtrl::SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md)|새 도구에 대 한 경계 사각형을 설정합니다.|  
|[CToolTipCtrl::SetWindowTheme](../Topic/CToolTipCtrl::SetWindowTheme.md)|도구 설명 창이의 시각적 스타일을 설정합니다.|  
|[CToolTipCtrl::Update](../Topic/CToolTipCtrl::Update.md)|현재 도구를 다시 그릴 수 있도록 해야 합니다.|  
|[CToolTipCtrl::UpdateTipText](../Topic/CToolTipCtrl::UpdateTipText.md)|도구에 대 한 도구 설명 텍스트를 설정합니다.|  
  
## 설명  
 "도구" 중 하나는 창 같은 자식 창 또는 컨트롤 또는 응용 프로그램 정의 사각형 영역 창의 클라이언트 영역 내에서입니다.  도구 설명이 있고 경우에 사용자가 커서를 도구 위에 배치 약 0.5 여 초 정도 그대로 나타나는 시간의 대부분 숨겨져 있습니다.  도구 설명은 커서 옆에 표시 및 사용자가 마우스 단추를 클릭 하거나 커서를 도구 밖으로 이동 하면 사라집니다.  
  
 `CToolTipCtrl`도구 설명 텍스트, 도구 설명 창이 자체와 공구 팁의 배경 및 텍스트 색상 주위의 여백 너비 시작 시간 및 기간 공구 팁의 제어 기능을 제공 합니다.  단일 tool tip 컨트롤 두 개 이상의 도구에 대 한 정보를 제공할 수 있습니다.  
  
 `CToolTipCtrl` 클래스는 Windows 공용 도구 설명 컨트롤의 기능을 제공 합니다.  이 컨트롤 \(즉의 `CToolTipCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 도구 설명을 활성화 하는 방법에 대 한 자세한 내용은 참조 하십시오.  [도구 팁 Cframewnd에서 파생 되지 windows에서](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 사용에 대 한 자세한 내용은 `CToolTipCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CToolTipCtrl을 사용 하 여](../../mfc/using-ctooltipctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)