---
title: "CSplitButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
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
  - "CSplitButton class"
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CSplitButton` 클래스 분할 단추 컨트롤을 나타냅니다.  분할 단추 컨트롤 사용자 주요 부분 단추를 클릭 하 고 드롭다운 화살표 단추를 클릭할 때 드롭다운 메뉴를 표시 하면 기본 동작을 수행 합니다.  
  
## 구문  
  
```  
class CSplitButton : public CButton  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSplitButton::CSplitButton](../Topic/CSplitButton::CSplitButton.md)|`CSplitButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSplitButton::Create](../Topic/CSplitButton::Create.md)|지정 된 스타일으로 분할 단추 컨트롤을 만들고 현재를 첨부 `CSplitButton` 개체입니다.|  
|[CSplitButton::SetDropDownMenu](../Topic/CSplitButton::SetDropDownMenu.md)|현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 드롭다운 메뉴를 설정 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSplitButton::OnDropDown](../Topic/CSplitButton::OnDropDown.md)|처리는 `BCN_DROPDOWN` 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 알림 시스템을 보냅니다.|  
  
## 설명  
 `CSplitButton` 클래스에서 파생 되는  [CButton](../../mfc/reference/cbutton-class.md) 클래스입니다.  분할 단추 컨트롤 스타일이 단추 컨트롤입니다 `BS_SPLITBUTTON`.  드롭다운 화살표를 클릭할 때 사용자 지정 메뉴를 표시 합니다.  자세한 내용은 `BS_SPLITBUTTON` 및 `BS_DEFSPLITBUTTON` 에서 스타일  [단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 다음 그림 \(1\) 분할 단추 컨트롤 페이저 컨트롤 포함 대화 상자를 보여 줍니다.  이미 \(2\) 드롭다운 화살표를 클릭 하 고 \(3\) 하위 메뉴를 표시 합니다.  
  
 ![splitbutton 및 pager 컨트롤이 있는 대화 상자](../../mfc/reference/media/splitbutton_pager.png "SplitButton\_Pager")  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## 요구 사항  
 **헤더:** afxcmn.h  
  
 이 클래스에서 지원 되지 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 이상.  
  
 이 클래스에 대 한 추가 요구 사항에서 설명 [Windows Vista 공용 컨트롤의 빌드 요구 사항](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
## 참고 항목  
 [CSplitButton Class](../../mfc/reference/csplitbutton-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)