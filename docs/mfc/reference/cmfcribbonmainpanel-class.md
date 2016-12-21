---
title: "CMFCRibbonMainPanel Class | Microsoft Docs"
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
  - "CMFCRibbonMainPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMainPanel class"
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonMainPanel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

누르면 표시 되는 리본 패널에 구현 된  [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## 구문  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|기본 생성자입니다.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonMainPanel::Add](../Topic/CMFCRibbonMainPanel::Add.md)|응용 프로그램 단추 패널의 왼쪽된 창에는 리본 요소를 추가합니다.  \(재정의 [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).\)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](../Topic/CMFCRibbonMainPanel::AddRecentFilesList.md)|최근에 사용한 파일 목록 메뉴에 텍스트 문자열을 추가합니다.|  
|[CMFCRibbonMainPanel::AddToBottom](../Topic/CMFCRibbonMainPanel::AddToBottom.md)|리본 응용 프로그램 창의 아래쪽 창에는 리본 요소를 추가합니다.|  
|[CMFCRibbonMainPanel::AddToRight](../Topic/CMFCRibbonMainPanel::AddToRight.md)|응용 프로그램 단추 패널의 오른쪽 창에는 리본 요소를 추가합니다.|  
|`CMFCRibbonMainPanel::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](../Topic/CMFCRibbonMainPanel::GetCommandsFrame.md)|기본 리본 패널의 영역을 나타내는 사각형을 반환 합니다.|  
|`CMFCRibbonMainPanel::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
  
## 설명  
 표시 된 프레임 워크는 `CMFCRibbonMainPanel` 응용 프로그램 패널을 엽니다.  이 세 개의 창이 있습니다.  
  
-   왼쪽된 창에 파일과 같은 관련 명령이  **열려**,  **저장**,  **인쇄**, 및  **닫기**.  이 창에 명령을 추가 하려면 호출 [CMFCRibbonMainPanel::Add](../Topic/CMFCRibbonMainPanel::Add.md).  
  
-   오른쪽 창의 왼쪽된 창에서 클릭 하 여 명령을 수정 하는 옵션을 포함 합니다.  예를 들어, 클릭 하면  **으로 저장** 왼쪽된 창에서 오른쪽 창의 사용할 수 있는 파일 형식을 표시할 수 있습니다.  이 창에 항목을 추가 하려면 호출 [CMFCRibbonMainPanel::AddToRight](../Topic/CMFCRibbonMainPanel::AddToRight.md).  
  
-   아래 구역 창의 프로그램을 종료 하 고 응용 프로그램의 설정을 변경할 수 있는 단추가 포함 되어 있습니다.  이 창에 항목을 추가 하려면 호출 [CMFCRibbonMainPanel::AddToBottom](../Topic/CMFCRibbonMainPanel::AddToBottom.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonMainPanel.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)