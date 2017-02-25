---
title: "CDragListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDragListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDragListBox class"
  - "drag list box [C++]"
  - "dragging list items"
  - "목록 상자"
  - "Windows[C++], 목록 상자"
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CDragListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 목록 상자의 기능을 제공 하는 것 외에 `CDragListBox` 클래스 파일 이름, 목록 상자의 항목 목록 상자 내에서 이동할 수 있습니다.  
  
## 구문  
  
```  
class CDragListBox : public CListBox  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDragListBox::CDragListBox](../Topic/CDragListBox::CDragListBox.md)|`CDragListBox` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDragListBox::BeginDrag](../Topic/CDragListBox::BeginDrag.md)|끌기 작업이 시작 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CDragListBox::CancelDrag](../Topic/CDragListBox::CancelDrag.md)|끌기 작업이 취소 되 면 프레임 워크에서 호출 됩니다.|  
|[CDragListBox::Dragging](../Topic/CDragListBox::Dragging.md)|프레임 워크에서 끌기 작업 중 이라고 합니다.|  
|[CDragListBox::DrawInsert](../Topic/CDragListBox::DrawInsert.md)|삽입 안내선을 끌어서 목록 상자를 그립니다.|  
|[CDragListBox::Dropped](../Topic/CDragListBox::Dropped.md)|항목이 삭제 된 후에 프레임 워크에서 호출 됩니다.|  
|[CDragListBox::ItemFromPt](../Topic/CDragListBox::ItemFromPt.md)|끌고 있는 항목을 반환 합니다.|  
  
## 설명  
 이 기능을 가진 목록 상자 항목 목록에 원하는 방식으로 하 여 유용한 것으로 수가 있습니다.  기본적으로 목록 상자 항목 목록의 새 위치로 이동 합니다.  그러나 `CDragListBox` 개체 항목을 이동 하지 않고 복사 하려면 사용자 수 있습니다.  
  
 목록 상자 컨트롤에 관련 된 `CDragListBox` 클래스에 있어야는  **LBS\_SORT** 또는  **LBS\_MULTIPLESELECT** 스타일.  목록 상자 스타일에 대 한 설명은 참조 하십시오.  [목록 상자 스타일](../../mfc/reference/list-box-styles.md).  
  
 끌어서 목록 상자에 기존 응용 프로그램의 대화 상자를 사용 하려면 대화 상자 편집기를 사용 하 여 대화 서식 파일에 목록 상자 컨트롤을 추가 하 고 다음 멤버 변수를 할당 \(범주 `Control` 및 변수 형식 `CDragListBox`\) 대화 서식 파일에 목록 상자 컨트롤에 해당 합니다.  
  
 멤버 변수를 할당 하는 컨트롤에 대 한 자세한 내용은  [바로 가기 대화 상자 컨트롤의 멤버 변수 정의 대 한](../../mfc/defining-member-variables-for-dialog-controls.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [Tstcon은 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)