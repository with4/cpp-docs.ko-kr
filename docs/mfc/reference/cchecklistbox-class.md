---
title: "CCheckListBox Class | Microsoft Docs"
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
  - "CCheckListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCheckListBox class"
  - "checklist boxes"
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCheckListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 확인 목록 상자의 기능을 제공합니다.  
  
## 구문  
  
```  
  
class CCheckListBox : public CListBox  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCheckListBox::CCheckListBox](../Topic/CCheckListBox::CCheckListBox.md)|`CCheckListBox` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCheckListBox::Create](../Topic/CCheckListBox::Create.md)|Windows 검사 목록 상자를 만들고 연결 하는 `CCheckListBox` 개체입니다.|  
|[CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md)|소유자 그리기 목록 상자 변경 내용을 시각적 측면이 때 프레임 워크에서 호출 됩니다.|  
|[CCheckListBox::Enable](../Topic/CCheckListBox::Enable.md)|확인 목록 상자 항목을 사용할 수 있거나.|  
|[CCheckListBox::GetCheck](../Topic/CCheckListBox::GetCheck.md)|항목의 확인란의 상태를 가져옵니다.|  
|[CCheckListBox::GetCheckStyle](../Topic/CCheckListBox::GetCheckStyle.md)|확인란 컨트롤의 스타일을 가져옵니다.|  
|[CCheckListBox::IsEnabled](../Topic/CCheckListBox::IsEnabled.md)|항목을 사용할 수 있는지 여부를 결정 합니다.|  
|[CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md)|목록 상자의 소유자 그리기 스타일을 만들 때 프레임 워크에 의해 호출 됩니다.|  
|[CCheckListBox::OnGetCheckPosition](../Topic/CCheckListBox::OnGetCheckPosition.md)|가져올 항목의 확인란의 위치는 프레임 워크에서 호출 됩니다.|  
|[CCheckListBox::SetCheck](../Topic/CCheckListBox::SetCheck.md)|항목의 확인란의 상태를 설정합니다.|  
|[CCheckListBox::SetCheckStyle](../Topic/CCheckListBox::SetCheckStyle.md)|확인란 컨트롤의 스타일을 설정합니다.|  
  
## 설명  
 "검사 목록 상자의" 파일 이름과 같은 항목의 목록을 표시합니다.  목록의 각 항목은 체크 상자 옆에 사용자가 선택 하거나 선택을 취소할 수 있습니다.  
  
 `CCheckListBox`목록 텍스트 문자열 보다 더 있기 때문에 소유자가 그린 컨트롤에만 있습니다.  가장 간단한 검사 목록 상자 확인란, 텍스트 문자열 포함 하지만 텍스트가 전혀 할 필요가 없습니다.  예를 들어, 목록을 작은 비트맵을 각 항목 옆에 확인란을 가질 수 있습니다.  
  
 자신의 검사 목록 상자를 만들려면 사용자 클래스에서 파생 되어야 `CCheckListBox`.  그런 다음 파생 클래스를 작성 하려면 파생된 클래스의 생성자를 호출  **만들기**.  
  
 목록 상자에서 해당 부모에 보낸 Windows 알림 메시지를 처리 하는 경우 \(일반적으로 클래스에서 파생 된  [CDialog](../../mfc/reference/cdialog-class.md)\), 각 메시지에 대 한 부모 클래스 메시지 맵 엔트리와 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 엔트리는 다음과 같은 형식을 사용합니다.  
  
 **ON\_**Notification**\(**`id`, `memberFxn`**\)**  
  
 위치 `id` 알림 메시지를 보내는 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 했다고 부모 멤버 함수의 이름입니다.  
  
 상위 함수 프로토타입은 다음과 같습니다.  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 구체적으로 관련 된 메시지 맵 항목이 하나만 있을  **CCheckListBox**  \(참조에 대 한 메시지 맵 항목  [clistbox 클래스](../../mfc/reference/clistbox-class.md)\).  
  
-   **ON\_CLBN\_CHKCHANGE** 항목의 확인란의 상태를 변경 합니다.  
  
 검사 목록 상자에 기본 검사 목록 상자 \(목록 기본 크기 확인란 왼쪽의 각 문자열\) 이면 기본 수  [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) 검사 목록 상자를 그립니다.  그렇지 않으면 무시 해야는  [CListBox::CompareItem](../Topic/CListBox::CompareItem.md) 함수 및  [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) 및  [CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md) 함수입니다.  
  
 검사 목록 상자에서 대화 상자 템플릿 또는 코드에서 직접 만들 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [Tstcon은 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)