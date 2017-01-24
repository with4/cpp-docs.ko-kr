---
title: "CMFCBaseVisualManager Class | Microsoft Docs"
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
  - "CMFCBaseVisualManager"
  - "CMFCBaseVisualManager.~CMFCBaseVisualManager"
  - "~CMFCBaseVisualManager"
  - "CMFCBaseVisualManager::~CMFCBaseVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseVisualManager destructor"
  - "CMFCBaseVisualManager class"
  - "CMFCBaseVisualManager class, 소멸자"
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCBaseVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파생 된 비주얼 관리자 및 Windows 테마 API 사이의 레이어.  
  
 `CMFCBaseVisualManager`Uxtheme.dll을 사용할 경우 로드 하 고 Windows 테마 API 메서드에 대 한 액세스를 관리 합니다.  
  
 이 클래스는 내부용입니다.  
  
## 구문  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](../Topic/CMFCBaseVisualManager::CMFCBaseVisualManager.md)|생성 및 초기화는 `CMFCBaseVisualManager` 개체입니다.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCBaseVisualManager::DrawCheckBox](../Topic/CMFCBaseVisualManager::DrawCheckBox.md)|현재 Windows 테마를 사용 하 여 checkbox 컨트롤을 그립니다.|  
|[CMFCBaseVisualManager::DrawComboBorder](../Topic/CMFCBaseVisualManager::DrawComboBorder.md)|현재 Windows 테마를 사용 하 여 콤보 상자 테두리를 그립니다.|  
|[CMFCBaseVisualManager::DrawComboDropButton](../Topic/CMFCBaseVisualManager::DrawComboDropButton.md)|현재 Windows 테마를 사용 하 여 콤보 상자 드롭다운 단추를 그립니다.|  
|[CMFCBaseVisualManager::DrawPushButton](../Topic/CMFCBaseVisualManager::DrawPushButton.md)|현재 Windows 테마를 사용 하 여 누름 단추를 그립니다.|  
|[CMFCBaseVisualManager::DrawRadioButton](../Topic/CMFCBaseVisualManager::DrawRadioButton.md)|현재 Windows 테마를 사용 하 여 라디오 단추 컨트롤을 그립니다.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](../Topic/CMFCBaseVisualManager::DrawStatusBarProgress.md)|상태 표시줄 컨트롤에는 진행률 표시줄을 그립니다 \([CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)\)는 현재 Windows 테마를 사용 합니다.|  
|[CMFCBaseVisualManager::FillReBarPane](../Topic/CMFCBaseVisualManager::FillReBarPane.md)|Rebar 컨트롤의 배경을 현재 Windows 테마를 사용 하 여 채웁니다.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](../Topic/CMFCBaseVisualManager::GetStandardWindowsTheme.md)|현재 Windows 테마를 가져옵니다.|  
  
### Protected 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCBaseVisualManager::CleanUpThemes](../Topic/CMFCBaseVisualManager::CleanUpThemes.md)|호출 `CloseThemeData` 에 모든 핸들을 얻을 대 한 `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](../Topic/CMFCBaseVisualManager::UpdateSystemColors.md)|호출 `OpenThemeData` 다양 한 컨트롤을 그리기에 대 한 핸들을 얻으려면: 창, 도구 모음, 단추 및 등.|  
  
## 설명  
 이 클래스의 개체를 직접 인스턴스화할 수 없습니다.  
  
 모든 비주얼 관리자에 대 한 기본 클래스 이므로 바로 호출 수 [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)에 대 한 포인터를 현재 비주얼 관리자 및 액세스 방법에 대 한 `CMFCBaseVisualManager` 해당 포인터를 사용 하 여.  현재 Windows 테마를 사용 하 여 컨트롤을 표시 하는 경우, 사용 하는 더 나은 것은 `CMFCVisualManagerWindows` 인터페이스.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxvisualmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)