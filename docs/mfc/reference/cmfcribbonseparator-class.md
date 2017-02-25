---
title: "CMFCRibbonSeparator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "GetThisClass"
  - "CMFCRibbonSeparator::GetThisClass"
  - "CMFCRibbonSeparator.CreateObject"
  - "CMFCRibbonSeparator::CreateObject"
  - "CMFCRibbonSeparator"
  - "CreateObject"
  - "CMFCRibbonSeparator.GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSeparator class"
  - "CreateObject method"
  - "GetThisClass method"
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMFCRibbonSeparator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 메뉴 구분 기호를 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](../Topic/CMFCRibbonSeparator::CMFCRibbonSeparator.md)|`CMFCRibbonSeparator` 개체를 생성합니다.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCRibbonSeparator::AddToListBox](../Topic/CMFCRibbonSeparator::AddToListBox.md)|구분 기호를 추가  **명령** 에  **사용자 지정** 대화 상자.  \(재정의 [CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md).\)|  
|`CMFCRibbonSeparator::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCRibbonSeparator::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
  
### Protected 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCRibbonSeparator::CopyFrom](../Topic/CMFCRibbonSeparator::CopyFrom.md)|구분의 멤버 변수가 다른 개체에서 설정 복사 방법입니다.|  
|[CMFCRibbonSeparator::GetRegularSize](../Topic/CMFCRibbonSeparator::GetRegularSize.md)|구분 기호를 반환합니다.|  
|[CMFCRibbonSeparator::IsSeparator](../Topic/CMFCRibbonSeparator::IsSeparator.md)|이 구분 기호 인지 여부를 나타냅니다.|  
|[CMFCRibbonSeparator::IsTabStop](../Topic/CMFCRibbonSeparator::IsTabStop.md)|이 탭 정지 인지 여부를 나타냅니다.|  
|[CMFCRibbonSeparator::OnDraw](../Topic/CMFCRibbonSeparator::OnDraw.md)|시스템 구분 기호 리본 또는 빠른 실행 도구 모음에서 그리기 위해 호출 됩니다.|  
|[CMFCRibbonSeparator::OnDrawOnList](../Topic/CMFCRibbonSeparator::OnDrawOnList.md)|구분선 그리기에서 시스템 호출을  **명령** 목록.|  
  
## 설명  
 리본 메뉴 구분 기호를 논리적으로 구분 요소 리본는 가로 또는 세로 선입니다.  리본 컨트롤, 기본 응용 프로그램 메뉴, 리본 상태 표시줄 및 빠른 액세스 도구 모음에 구분선을 그릴 수 있습니다.  
  
 응용 프로그램에는 구분 기호를 사용 하려면 새 개체를 생성 하 고 다음과 같이 기본 응용 프로그램 메뉴에 추가:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"), IDB_FILESMALL, IDB_FILELARGE);   
...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));  
```  
  
 호출 [CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md) 리본 패널에 구분 기호를 추가 합니다.  구분 기호를 할당 하 고 내부적으로 추가 된 `AddSeparator` 메서드.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## 요구 사항  
 **헤더:** afxbaseribbonelement.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)