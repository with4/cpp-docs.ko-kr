---
title: "CLinkCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinkCtrl class"
  - "컨트롤[MFC], 링크"
  - "링크[C++], link control"
  - "SysLink control"
  - "웹 페이지, link control"
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적인 Windows SysLink 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CLinkCtrl::CLinkCtrl](../Topic/CLinkCtrl::CLinkCtrl.md)|`CLinkCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CLinkCtrl::Create](../Topic/CLinkCtrl::Create.md)|링크 컨트롤을 만들고이에 연결 된 `CLinkCtrl` 개체입니다.|  
|[CLinkCtrl::CreateEx](../Topic/CLinkCtrl::CreateEx.md)|링크 컨트롤 확장된 스타일을 만들고 연결 하는 `CLinkCtrl` 개체입니다.|  
|[CLinkCtrl::GetIdealHeight](../Topic/CLinkCtrl::GetIdealHeight.md)|링크 컨트롤의 이상적인 높이 검색합니다.|  
|[CLinkCtrl::GetIdealSize](../Topic/CLinkCtrl::GetIdealSize.md)|링크 텍스트 링크의 지정 된 너비에 따라 현재 연결 컨트롤의 기본 설정된 높이 계산합니다.|  
|[CLinkCtrl::GetItem](../Topic/CLinkCtrl::GetItem.md)|상태 및 링크 컨트롤 항목의 속성을 검색합니다.|  
|[CLinkCtrl::GetItemID](../Topic/CLinkCtrl::GetItemID.md)|링크 컨트롤 항목의 ID를 검색합니다.|  
|[CLinkCtrl::GetItemState](../Topic/CLinkCtrl::GetItemState.md)|링크 컨트롤 항목의 상태를 검색합니다.|  
|[CLinkCtrl::GetItemUrl](../Topic/CLinkCtrl::GetItemUrl.md)|링크 컨트롤 항목으로 표현 되는 URL을 검색 합니다.|  
|[CLinkCtrl::HitTest](../Topic/CLinkCtrl::HitTest.md)|사용자 지정 된 링크 클릭 여부를 결정 합니다.|  
|[CLinkCtrl::SetItem](../Topic/CLinkCtrl::SetItem.md)|상태 및 링크 컨트롤 항목의 속성을 설정합니다.|  
|[CLinkCtrl::SetItemID](../Topic/CLinkCtrl::SetItemID.md)|링크 컨트롤 항목의 ID를 설정 합니다.|  
|[CLinkCtrl::SetItemState](../Topic/CLinkCtrl::SetItemState.md)|링크 컨트롤 항목의 상태를 설정합니다.|  
|[CLinkCtrl::SetItemUrl](../Topic/CLinkCtrl::SetItemUrl.md)|링크 컨트롤 항목으로 표현 되는 URL을 설정 합니다.|  
  
## 설명  
 "연결 컨트롤" 창에 하이퍼텍스트 링크를 포함 하는 편리한 방법을 제공 합니다.  실제 컨트롤에 표시 된 텍스트를 렌더링 하는 포함 된 링크를 클릭할 때 적절 한 응용 프로그램을 실행 하는 창입니다.  여러 링크 컨트롤 내에서 지원 되며 인덱스에 액세스할 수 있습니다.  
  
 이 컨트롤 \(즉의 `CLinkCtrl` 클래스\) 및 나중에 Windows xp를 실행 하는 프로그램에만 사용할 수 있습니다.  
  
 자세한 내용은  [SysLink 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb760706) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## 요구 사항  
 **헤더:** afxcmn.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)