---
title: "CScrollBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CScrollBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[MFC], 스크롤 막대"
  - "CScrollBar class"
  - "스크롤 막대"
  - "SCROLLBAR window class"
  - "Windows common controls [C++], CScrollBar"
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CScrollBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 스크롤 막대 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CScrollBar : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CScrollBar::CScrollBar](../Topic/CScrollBar::CScrollBar.md)|`CScrollBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CScrollBar::Create](../Topic/CScrollBar::Create.md)|Windows 스크롤 막대를 만들고 연결 하는 `CScrollBar` 개체입니다.|  
|[CScrollBar::EnableScrollBar](../Topic/CScrollBar::EnableScrollBar.md)|스크롤 막대의 한쪽 또는 양쪽 화살표를 사용할 수 있거나.|  
|[CScrollBar::GetScrollBarInfo](../Topic/CScrollBar::GetScrollBarInfo.md)|스크롤 막대를 사용 하 여 정보 검색은 `SCROLLBARINFO` 구조.|  
|[CScrollBar::GetScrollInfo](../Topic/CScrollBar::GetScrollInfo.md)|스크롤 막대에 대 한 정보를 검색합니다.|  
|[CScrollBar::GetScrollLimit](../Topic/CScrollBar::GetScrollLimit.md)|스크롤 막대의 한계를 검색합니다.|  
|[CScrollBar::GetScrollPos](../Topic/CScrollBar::GetScrollPos.md)|스크롤 상자의 현재 위치를 검색합니다.|  
|[CScrollBar::GetScrollRange](../Topic/CScrollBar::GetScrollRange.md)|현재 지정 된 스크롤 막대의 최소 및 최대 스크롤 막대 위치를 검색합니다.|  
|[CScrollBar::SetScrollInfo](../Topic/CScrollBar::SetScrollInfo.md)|스크롤 막대에 대 한 정보를 설정합니다.|  
|[CScrollBar::SetScrollPos](../Topic/CScrollBar::SetScrollPos.md)|스크롤 상자의 현재 위치를 설정합니다.|  
|[CScrollBar::SetScrollRange](../Topic/CScrollBar::SetScrollRange.md)|지정 된 스크롤 막대의 최소 및 최대 위치 값을 설정합니다.|  
|[CScrollBar::ShowScrollBar](../Topic/CScrollBar::ShowScrollBar.md)|표시 하거나 스크롤 막대를 숨깁니다.|  
  
## 설명  
 두 단계에서 스크롤 막대 컨트롤을 만듭니다.  먼저 생성자 호출 `CScrollBar` 생성 하는 `CScrollBar` 개체를 호출 하 고는  [만들기](../Topic/CScrollBar::Create.md) Windows 스크롤 막대 컨트롤에 연결 하는 멤버 함수는 `CScrollBar` 개체.  
  
 만들 경우는 `CScrollBar` 대화 상자 \(대화 상자 리소스\)를 통해 개체는 `CScrollBar` 대화 상자를 닫으면 자동으로 소멸 됩니다.  
  
 만들 경우는 `CScrollBar` 해야 파괴 하는 창 내의 개체입니다.  
  
 사용자가 만든 경우는 `CScrollBar` 개체는 스택에 자동으로 소멸 됩니다.  만들 경우의 `CScrollBar` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** Windows 스크롤 막대는 사용자가 종료 되 면 파기 하는 개체.  
  
 모든 메모리를 할당 하는 경우는 `CScrollBar` 개체, 재정의 `CScrollBar` 할당을 삭제 하는 소멸자입니다.  
  
 사용에 대 한 관련된 정보에 대 한 `CScrollBar`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)