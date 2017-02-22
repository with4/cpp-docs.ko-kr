---
title: "CSliderCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSliderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl class"
  - "CSliderCtrl class, 공용 컨트롤"
  - "슬라이더 컨트롤, CSliderCtrl class"
  - "Windows common controls [C++], CSliderCtrl"
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSliderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 일반 슬라이더 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSliderCtrl::CSliderCtrl](../Topic/CSliderCtrl::CSliderCtrl.md)|`CSliderCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSliderCtrl::ClearSel](../Topic/CSliderCtrl::ClearSel.md)|슬라이더 컨트롤의 현재 선택 영역을 지웁니다.|  
|[CSliderCtrl::ClearTics](../Topic/CSliderCtrl::ClearTics.md)|현재 눈금 표시가 slider 컨트롤에서 제거합니다.|  
|[CSliderCtrl::Create](../Topic/CSliderCtrl::Create.md)|슬라이더 컨트롤을 만들고이에 연결 된 `CSliderCtrl` 개체입니다.|  
|[CSliderCtrl::CreateEx](../Topic/CSliderCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 슬라이더 컨트롤을 만들고이에 연결 된 `CSliderCtrl` 개체입니다.|  
|[CSliderCtrl::GetBuddy](../Topic/CSliderCtrl::GetBuddy.md)|지정 된 위치에 있는 슬라이더 컨트롤 버디 창 핸들을 검색합니다.|  
|[CSliderCtrl::GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md)|슬라이더 컨트롤 채널의 크기를 검색합니다.|  
|[CSliderCtrl::GetLineSize](../Topic/CSliderCtrl::GetLineSize.md)|슬라이더 컨트롤의 줄 크기를 검색합니다.|  
|[CSliderCtrl::GetNumTics](../Topic/CSliderCtrl::GetNumTics.md)|슬라이더 컨트롤의 눈금 표시 수를 검색합니다.|  
|[CSliderCtrl::GetPageSize](../Topic/CSliderCtrl::GetPageSize.md)|슬라이더 컨트롤의 페이지 크기를 검색합니다.|  
|[CSliderCtrl::GetPos](../Topic/CSliderCtrl::GetPos.md)|슬라이더의 현재 위치를 검색합니다.|  
|[CSliderCtrl::GetRange](../Topic/CSliderCtrl::GetRange.md)|슬라이더의 최소 및 최대 위치를 검색합니다.|  
|[CSliderCtrl::GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md)|슬라이더의 최대 위치를 검색합니다.|  
|[CSliderCtrl::GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md)|슬라이더의 최소 위치를 검색합니다.|  
|[CSliderCtrl::GetSelection](../Topic/CSliderCtrl::GetSelection.md)|현재 선택 영역의 범위를 검색합니다.|  
|[CSliderCtrl::GetThumbLength](../Topic/CSliderCtrl::GetThumbLength.md)|현재 trackbar 컨트롤에서은 슬라이더의 길이 검색합니다.|  
|[CSliderCtrl::GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md)|엄지 슬라이더 컨트롤의 크기를 검색합니다.|  
|[CSliderCtrl::GetTic](../Topic/CSliderCtrl::GetTic.md)|지정 된 눈금 표시의 위치를 검색합니다.|  
|[CSliderCtrl::GetTicArray](../Topic/CSliderCtrl::GetTicArray.md)|슬라이더 컨트롤의 눈금 표시 위치 배열을 검색합니다.|  
|[CSliderCtrl::GetTicPos](../Topic/CSliderCtrl::GetTicPos.md)|클라이언트 좌표에서 지정 된 눈금 표시의 위치를 검색합니다.|  
|[CSliderCtrl::GetToolTips](../Topic/CSliderCtrl::GetToolTips.md)|있는 경우 슬라이더 컨트롤에 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|  
|[CSliderCtrl::SetBuddy](../Topic/CSliderCtrl::SetBuddy.md)|창 버디 창 슬라이더 컨트롤에 할당합니다.|  
|[CSliderCtrl::SetLineSize](../Topic/CSliderCtrl::SetLineSize.md)|슬라이더 컨트롤의 줄 크기를 설정합니다.|  
|[CSliderCtrl::SetPageSize](../Topic/CSliderCtrl::SetPageSize.md)|슬라이더 컨트롤의 페이지 크기를 설정합니다.|  
|[CSliderCtrl::SetPos](../Topic/CSliderCtrl::SetPos.md)|슬라이더의 현재 위치를 설정합니다.|  
|[CSliderCtrl::SetRange](../Topic/CSliderCtrl::SetRange.md)|최소 및 최대 위치 슬라이더를 설정합니다.|  
|[CSliderCtrl::SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md)|슬라이더의 최대 위치를 설정합니다.|  
|[CSliderCtrl::SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md)|슬라이더의 최소 위치를 설정합니다.|  
|[CSliderCtrl::SetSelection](../Topic/CSliderCtrl::SetSelection.md)|현재 선택 영역의 범위를 설정합니다.|  
|[CSliderCtrl::SetThumbLength](../Topic/CSliderCtrl::SetThumbLength.md)|현재 trackbar 컨트롤에 슬라이더의 길이 설정합니다.|  
|[CSliderCtrl::SetTic](../Topic/CSliderCtrl::SetTic.md)|지정 된 눈금 표시의 위치를 설정합니다.|  
|[CSliderCtrl::SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md)|주파수의 틱 당 슬라이더 컨트롤 증가 설정입니다.|  
|[CSliderCtrl::SetTipSide](../Topic/CSliderCtrl::SetTipSide.md)|Trackbar 컨트롤에서 도구 설명 컨트롤을 사용 하는 위치.|  
|[CSliderCtrl::SetToolTips](../Topic/CSliderCtrl::SetToolTips.md)|도구 설명 컨트롤에 슬라이더 컨트롤에 할당합니다.|  
  
## 설명  
 "Slider 컨트롤" \(trackbar\) 슬라이더 및 선택적 눈금 포함 하는 창입니다.  마우스나 방향 키를 사용 하 여 슬라이더를 이동할 때 컨트롤의 변경을 나타내는 알림 메시지를 보냅니다.  
  
 슬라이더 컨트롤 불연속적인 값 또는 연속적인 값 범위에서 선택 하도록 할 때 유용 합니다.  예를 들어, 지정 된 눈금 표시로 슬라이더를 이동 하 여 키보드의 반복 속도 설정할 수 있도록 하려면 슬라이더 컨트롤을 사용할 수 있습니다.  
  
 이 컨트롤 \(즉의 `CSliderCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 만들 때 사용자가 지정한 간격으로 슬라이더를 이동 합니다.  슬라이더의 범위를 다섯으로 지정한 경우 예를 들어, 슬라이더는 여섯 개의 위치 차지할 수: 범위에 있는 각 증가값에 대해 하나의 위치 슬라이더 컨트롤의 왼쪽에 위치 합니다.  일반적으로 이러한 위치 중 각 눈금으로 식별 합니다.  
  
 생성자를 사용 하 여 슬라이더를 생성 하는  **만들기** 멤버 함수를 `CSliderCtrl`.  슬라이더 컨트롤을 작성 한 후에 멤버 함수를 사용할 수 있습니다 `CSliderCtrl` 대부분의 속성을 변경 합니다.  수행할 수 있는 변경 슬라이더에 대 한 최소 및 최대 위치 설정, 눈금 표시 그리기, 선택 범위를 설정 및 슬라이더 위치 조정 포함 됩니다.  
  
 사용에 대 한 자세한 내용은 `CSliderCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CSliderCtrl 사용](../../mfc/using-csliderctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl Class](../../mfc/reference/cprogressctrl-class.md)