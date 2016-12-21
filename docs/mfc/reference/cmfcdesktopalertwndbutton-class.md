---
title: "CMFCDesktopAlertWndButton Class | Microsoft Docs"
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
  - "CMFCDesktopAlertWndButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndButton class"
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWndButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단추를 데스크톱 경고 대화 상자에 추가할 수 있습니다.  
  
## 구문  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|기본 생성자입니다.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](../Topic/CMFCDesktopAlertWndButton::IsCaptionButton.md)|경고 대화 상자 캡션 영역의 단추를 표시할지 여부를 결정 합니다.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](../Topic/CMFCDesktopAlertWndButton::IsCloseButton.md)|단추가 경고 대화 상자가 닫힙니다 여부를 결정 합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|경고 대화 상자 캡션 영역의 단추를 표시할지 여부를 지정 하는 부울 값입니다.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|단추가 경고 대화 상자가 닫힐 지 여부를 지정 하는 부울 값입니다.|  
  
### 설명  
 기본적으로 설정 하는 생성자는 `m_bIsCaptionButton` 및 `m_bIsCloseButton` 데이터 멤버를 `FALSE`.  부모 `CMFCDesktopAlertDialog` 개체 집합 `m_bIsCaptionButton` 에 `TRUE` 단추 캡션 영역의 경고 대화 상자에서 배치 된 경우.  `CMFCDesktopAlertDialog` 클래스를 만듭니다는 `CMFCDesktopAlertWndButton` 역할을 경고 대화 상자를 닫는 단추 설정 선택한 개체 `m_bIsCloseButton` 에 `TRUE`.  
  
 추가 `CMFCDesktopAlertWndButton` 개체에 `CMFCDesktopAlertDialog` 개체는 단추를 추가할 때 처럼.  `CMFCDesktopAlertDialog`에 대한 자세한 내용은 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `SetImage` 메서드에서 `CMFCDesktopAlertWndButton` 클래스입니다.  이 코드 조각에 속하지는  [바탕 화면 경고 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxdesktopalertwnd.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)