---
title: "CReBar Class | Microsoft Docs"
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
  - "CReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar class"
  - "Internet Explorer 4.0 common controls"
  - "rebar controls, control bar"
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤 막대 레이아웃, 지 속성 및 rebar 컨트롤에 대 한 상태 정보를 제공 합니다.  
  
## 구문  
  
```  
  
class CReBar : public CControlBar  
  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CReBar::AddBar](../Topic/CReBar::AddBar.md)|밴드를 rebar를 추가합니다.|  
|[CReBar::Create](../Topic/CReBar::Create.md)|Rebar 컨트롤을 만들고이에 연결 된 `CReBar` 개체입니다.|  
|[CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md)|내부 공용 컨트롤에 직접 액세스할 수 있습니다.|  
  
## 설명  
 Rebar 개체는 다양 한 자식 창, 도구 모음, 입력란, 목록 상자를 포함 하 여 일반적으로 다른 컨트롤을 포함할 수 있습니다.  Rebar 개체는 지정 된 비트맵 위에 자식 창 표시할 수 있습니다.  응용 프로그램 자동 rebar 하거나 사용자가 수동으로 rebar 클릭 하거나 해당 그리퍼 막대를 드래그 하 여 조정할 수 있습니다.  
  
 ![RebarMenu의 예](../../mfc/reference/media/vc4sc61.png "vc4SC61")  
  
## Rebar 컨트롤  
 Rebar 개체는 마찬가지로 도구 모음 개체를 작동합니다.  Rebar 밴드의 크기를 조정 하려면을 클릭 하 고 드래그 메커니즘을 사용 합니다.  Rebar 컨트롤은 각 밴드는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창 조합으로 하나 이상의 밴드를 포함할 수 있습니다.  그러나 밴드는 둘 이상의 자식 창을 포함할 수 없습니다.  
  
 **CReBar** 를 사용 하는  [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 클래스의 구현을 제공 합니다.  Rebar 컨트롤을 통해 액세스할 수 있는  [GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) 컨트롤의 사용자 지정 옵션을 활용 합니다.  Rebar 컨트롤에 대 한 자세한 내용은 `CReBarCtrl`.  Rebar 컨트롤 사용에 대 한 자세한 내용은  [CReBarCtrl 사용](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  철근 및 rebar 컨트롤 개체 MFC 컨트롤 막대 도킹을 지원 하지 않습니다.  경우  **CRebar::EnableDocking** 호출, 응용 프로그램을 가정 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [MFCIE MFC 샘플](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)