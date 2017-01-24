---
title: "CPagerCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPagerCtrl class"
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPagerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPagerCtrl` 클래스 배치 Windows 페이저 컨트롤을 보기에 포함 된 창은 상단에 맞지 않는 스크롤할 수 있습니다.  
  
## 구문  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPagerCtrl::CPagerCtrl](../Topic/CPagerCtrl::CPagerCtrl.md)|`CPagerCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPagerCtrl::Create](../Topic/CPagerCtrl::Create.md)|지정 된 스타일으로 페이저 컨트롤을 만들고 현재를 첨부 `CPagerCtrl` 개체입니다.|  
|[CPagerCtrl::CreateEx](../Topic/CPagerCtrl::CreateEx.md)|지정한 확장된 스타일을 페이저 컨트롤을 만들고 현재를 첨부 `CPagerCtrl` 개체입니다.|  
|[CPagerCtrl::ForwardMouse](../Topic/CPagerCtrl::ForwardMouse.md)|전달을 사용 하거나  [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) 메시지를 현재 페이저 컨트롤에 포함 된 창입니다.|  
|[CPagerCtrl::GetBkColor](../Topic/CPagerCtrl::GetBkColor.md)|현재 페이저 컨트롤의 배경 색을 검색합니다.|  
|[CPagerCtrl::GetBorder](../Topic/CPagerCtrl::GetBorder.md)|현재 페이저 컨트롤의 테두리 크기를 검색합니다.|  
|[CPagerCtrl::GetButtonSize](../Topic/CPagerCtrl::GetButtonSize.md)|현재 페이저 컨트롤의 단추 크기를 검색합니다.|  
|[CPagerCtrl::GetButtonState](../Topic/CPagerCtrl::GetButtonState.md)|현재 페이저 컨트롤에서 지정 된 단추의 상태를 검색합니다.|  
|[CPagerCtrl::GetDropTarget](../Topic/CPagerCtrl::GetDropTarget.md)|검색은  [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) 인터페이스 현재 페이저 컨트롤입니다.|  
|[CPagerCtrl::GetScrollPos](../Topic/CPagerCtrl::GetScrollPos.md)|현재 페이저 컨트롤의 스크롤 위치를 검색합니다.|  
|[CPagerCtrl::IsButtonDepressed](../Topic/CPagerCtrl::IsButtonDepressed.md)|지정한 단추의 현재 페이저 컨트롤에 있는지 여부를 나타내는 `pressed` 상태.|  
|[CPagerCtrl::IsButtonGrayed](../Topic/CPagerCtrl::IsButtonGrayed.md)|지정한 단추의 현재 페이저 컨트롤에 있는지 여부를 나타내는 `grayed` 상태.|  
|[CPagerCtrl::IsButtonHot](../Topic/CPagerCtrl::IsButtonHot.md)|지정한 단추의 현재 페이저 컨트롤에 있는지 여부를 나타내는 `hot` 상태.|  
|[CPagerCtrl::IsButtonInvisible](../Topic/CPagerCtrl::IsButtonInvisible.md)|지정한 단추의 현재 페이저 컨트롤에 있는지 여부를 나타내는 `invisible` 상태.|  
|[CPagerCtrl::IsButtonNormal](../Topic/CPagerCtrl::IsButtonNormal.md)|지정한 단추의 현재 페이저 컨트롤에 있는지 여부를 나타내는 `normal` 상태.|  
|[CPagerCtrl::RecalcSize](../Topic/CPagerCtrl::RecalcSize.md)|현재 페이저 컨트롤에 포함 된 창의 크기를 다시 계산 됩니다.|  
|[CPagerCtrl::SetBkColor](../Topic/CPagerCtrl::SetBkColor.md)|현재 페이저 컨트롤의 배경색을 설정합니다.|  
|[CPagerCtrl::SetBorder](../Topic/CPagerCtrl::SetBorder.md)|현재 페이저 컨트롤의 테두리 크기를 설정합니다.|  
|[CPagerCtrl::SetButtonSize](../Topic/CPagerCtrl::SetButtonSize.md)|현재 페이저 컨트롤의 단추 크기를 설정합니다.|  
|[CPagerCtrl::SetChild](../Topic/CPagerCtrl::SetChild.md)|포함 된 창은 현재 페이저 컨트롤을 설정합니다.|  
|[CPagerCtrl::SetScrollPos](../Topic/CPagerCtrl::SetScrollPos.md)|현재 페이저 컨트롤의 스크롤 위치를 설정합니다.|  
  
## 설명  
 페이저 컨트롤 선형 및 포함 하는 창을 보다 큰 포함 된 창 보기로 스크롤할 수 있도록 다른 창을 포함 하는 창입니다.  페이저 컨트롤 포함 된 창을 스크롤할 때 가장 정도 자동으로 사라지는 두 스크롤 단추를 표시 하 고 그렇지 않으면 다시.  가로 또는 세로로 스크롤 하는 페이저 컨트롤을 만들 수 있습니다.  
  
 예를 들어, 응용 프로그램 도구 모음이 해당 항목을 모두 표시 하기에 충분 하지 않은 경우 페이저 컨트롤에 도구 모음을 지정할 수 있습니다 및 사용자가 도구 모음을 왼쪽 이나 오른쪽의 모든 항목에 액세스할 수를 스크롤할 수 있습니다.  페이저 컨트롤 Microsoft Internet Explorer 버전 4.0 \(commctrl.dll 버전 4.71\)를 소개합니다.  
  
 `CPagerCtrl` 클래스에서 파생 되는  [CWnd](../../mfc/reference/cwnd-class.md) 클래스입니다.  자세한 내용과 그림 페이저 컨트롤의  [페이저 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## 요구 사항  
 **헤더:** afxcmn.h  
  
## 참고 항목  
 [CPagerCtrl Class](../../mfc/reference/cpagerctrl-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [페이저 컨트롤입니다.](http://msdn.microsoft.com/library/windows/desktop/bb760855)