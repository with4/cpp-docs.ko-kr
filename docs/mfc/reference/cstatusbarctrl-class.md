---
title: "CStatusBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl class"
  - "status bar controls"
  - "Windows common controls [C++], CStatusBarCtrl"
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStatusBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 공용 상태 표시줄 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CStatusBarCtrl::CStatusBarCtrl](../Topic/CStatusBarCtrl::CStatusBarCtrl.md)|`CStatusBarCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStatusBarCtrl::Create](../Topic/CStatusBarCtrl::Create.md)|상태 표시줄 컨트롤을 만들고이에 연결 된 `CStatusBarCtrl` 개체입니다.|  
|[CStatusBarCtrl::CreateEx](../Topic/CStatusBarCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 상태 표시줄 컨트롤을 만들고이에 연결 된 `CStatusBarCtrl` 개체입니다.|  
|[CStatusBarCtrl::DrawItem](../Topic/CStatusBarCtrl::DrawItem.md)|시각적 측면이 소유자 그리기 상태 표시줄 컨트롤이 변경 되 면 호출 됩니다.|  
|[CStatusBarCtrl::GetBorders](../Topic/CStatusBarCtrl::GetBorders.md)|현재 상태 표시줄 컨트롤의 가로 및 세로 테두리의 너비를 검색합니다.|  
|[CStatusBarCtrl::GetIcon](../Topic/CStatusBarCtrl::GetIcon.md)|현재 상태 표시줄 컨트롤에 일부 \(창\)에 대 한 아이콘을 검색합니다.|  
|[CStatusBarCtrl::GetParts](../Topic/CStatusBarCtrl::GetParts.md)|상태 표시줄 컨트롤에 있는 부품의 개수를 검색합니다.|  
|[CStatusBarCtrl::GetRect](../Topic/CStatusBarCtrl::GetRect.md)|상태 표시줄 컨트롤에 파트의 경계 사각형을 검색합니다.|  
|[CStatusBarCtrl::GetText](../Topic/CStatusBarCtrl::GetText.md)|상태 표시줄 컨트롤의 특정된 부분에서 텍스트를 검색합니다.|  
|[CStatusBarCtrl::GetTextLength](../Topic/CStatusBarCtrl::GetTextLength.md)|상태 표시줄 컨트롤의 특정된 부분에서 텍스트의 문자 길이 검색 합니다.|  
|[CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md)|상태 표시줄에 있는 창에 대 한 도구 설명 텍스트를 검색합니다.|  
|[CStatusBarCtrl::IsSimple](../Topic/CStatusBarCtrl::IsSimple.md)|단순 모드에 있는지 확인 하려면 상태 창 컨트롤을 확인 합니다.|  
|[CStatusBarCtrl::SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md)|상태 표시줄의 배경 색을 설정 합니다.|  
|[CStatusBarCtrl::SetIcon](../Topic/CStatusBarCtrl::SetIcon.md)|상태 표시줄에 있는 창 아이콘을 설정합니다.|  
|[CStatusBarCtrl::SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)|최소 높이 상태 표시줄 컨트롤의 그리기 영역을 설정합니다.|  
|[CStatusBarCtrl::SetParts](../Topic/CStatusBarCtrl::SetParts.md)|부품의 상태 표시줄 컨트롤 및 각 부품의 오른쪽 가장자리의 좌표를에서 설정합니다.|  
|[CStatusBarCtrl::SetSimple](../Topic/CStatusBarCtrl::SetSimple.md)|상태 표시줄 컨트롤 간단한 텍스트 표시 이전 호출에 의해 설정 된 모든 컨트롤 구성 요소 표시 여부를 지정 `SetParts`.|  
|[CStatusBarCtrl::SetText](../Topic/CStatusBarCtrl::SetText.md)|해당된 부품의 상태 표시줄 컨트롤에 텍스트를 설정합니다.|  
|[CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md)|상태 표시줄에 있는 창에 대 한 도구 설명 텍스트를 설정합니다.|  
  
## 설명  
 "상태 표시줄 컨트롤"은 일반적으로 응용 프로그램에 다양 한 종류의 상태 정보를 표시할 수 있는 부모 창의 맨 아래에 표시 하는 가로 창입니다.  상태 표시줄 컨트롤은 여러 유형의 정보를 표시 하는 부분으로 나눌 수 있습니다.  
  
 이 컨트롤 \(즉의 `CStatusBarCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `CStatusBarCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CStatusBarCtrl을 사용 하 여](../../mfc/using-cstatusbarctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatusBarCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)