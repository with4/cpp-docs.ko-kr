---
title: "CDockState Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockState class"
  - "dock state"
  - "docking control bars"
  - "docking tool windows"
  - "위치, control bar"
  - "크기"
  - "크기, control bar"
  - "상태, dockable control bar"
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDockState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Serialize 된 `CObject` 막대를 영구 메모리 \(파일\)에서 클래스 로드, 언로드, 또는 하나 이상의 도킹 된 컨트롤의 상태를 지웁니다.  
  
## 구문  
  
```  
class CDockState : public CObject  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDockState::Clear](../Topic/CDockState::Clear.md)|도킹 상태 정보를 지웁니다.|  
|[CDockState::GetVersion](../Topic/CDockState::GetVersion.md)|버전 번호는 저장 된 검색 막대 상태.|  
|[CDockState::LoadState](../Topic/CDockState::LoadState.md)|검색 상태 정보를 모두 제거에서 하거나.INI 파일입니다.|  
|[CDockState::SaveState](../Topic/CDockState::SaveState.md)|레지스트리 파일이 나 INI 파일에 상태 정보를 저장합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDockState::m\_arrBarInfo](../Topic/CDockState::m_arrBarInfo.md)|포인터를 저장 하는 배열을 고정 각 컨트롤 막대에 대 한 항목과 함께 상태 정보.|  
  
## 설명  
 크기 및 위치 표시줄과 도킹 여부의 도킹 상태를 포함 합니다.  상태 때 도킹는 저장 된 검색 `CDockState` 막대의 검사 위치 및 막대를 화면에 현재 설정으로 표시 되지 않으면 `CDockState` 막대의 크기를 조정 위치를 볼 수 있도록 합니다.  주 목적은 `CDockState` 컨트롤 막대의 전체 상태를 저장 하 고 해당 상태를 저장 하도록 허용 하 고 레지스트리의 응용 프로그램에 로드 합니다.INI 파일 또는 이진 형식으로 `CArchive` 개체의 내용을.  
  
 막대 표시줄, 도구 모음, 상태 표시줄 또는 대화 상자 막대를 포함 하 여 모든 도킹 가능한 제어 될 수 있습니다.  `CDockState`개체를 작성 하 고 읽기를 통해 파일을 `CArchive` 개체.  
  
 [CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md) 프레임 창의 모든 상태 정보를 검색 합니다. `CControlBar` 에 배치 하 고 개체의 `CDockState` 개체.  다음의 내용을 작성할 수 있습니다는 `CDockState` 개체를 저장소에  [Serialize](../Topic/CObject::Serialize.md) 또는  [CDockState::SaveState](../Topic/CDockState::SaveState.md).  나중에 컨트롤 막대는 프레임 창에서 상태를 복원 하려면 상태를 로드할 수 있습니다 `Serialize` 또는  [CDockState::LoadState](../Topic/CDockState::LoadState.md), 다음 사용  [CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md) 상태 저장된 프레임 창의 컨트롤 막대에 적용 합니다.  
  
 컨트롤 막대 도킹에 대 한 자세한 내용은 문서를 참조 하십시오.  [컨트롤 막대](../../mfc/control-bars.md),  [도구 모음: 도킹 및 부동](../../mfc/docking-and-floating-toolbars.md), 및  [프레임 Windows](../../mfc/frame-windows.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## 요구 사항  
 **헤더:**  afxadv.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)