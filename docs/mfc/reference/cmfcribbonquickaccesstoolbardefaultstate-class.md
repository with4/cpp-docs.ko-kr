---
title: "CMFCRibbonQuickAccessToolBarDefaultState Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonQuickAccessToolBarDefaultState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonQuickAccessToolBarDefaultState class"
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCRibbonQuickAccessToolBarDefaultState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빠른 액세스 도구 리본 메뉴 모음에 위치 하 고 모음에 대 한 기본 상태를 관리 하는 도우미 클래스 \([CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)\).  
  
## 구문  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState.md)|`CMFCRibbonQuickAccessToolbarDefaultState` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand.md)|명령을 기본 상태로 빠른 실행 도구 모음을 추가합니다.  도구 모음 자체는 변경 되지 않습니다.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom.md)|속성 빠른 액세스 도구 모음을 다른 위치로 복사합니다.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](../Topic/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll.md)|모든 명령을 빠른 실행 도구 모음에서 제거합니다.  도구 모음 자체는 변경 되지 않습니다.|  
  
## 설명  
 빠른 액세스 도구 모음에서 응용 프로그램을 만든 후 호출 하 여 기본 상태를 설정 하는 좋습니다 [CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md).  클릭할 때이 기본 상태로 복원 되는  **재설정** 단추는  **사용자 지정** 페이지의 응용 프로그램의  **옵션** 대화 상자.  
  
## 상속 계층 구조  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## 예제  
 다음 예제에서는 개체를 생성 하는 방법을 보여 줍니다.을 `CMFCRibbonQuickAccessToolbarDefaultState` 클래스와 명령을 기본 상태로 빠른 실행 도구 모음을 추가 하는 방법.  
  
 [!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/CPP/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## 요구 사항  
 **헤더:** afxribbonquickaccesstoolbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)