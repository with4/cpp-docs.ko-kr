---
title: "CStatic Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비트맵, 표시"
  - "컨트롤[MFC], static"
  - "CStatic class"
  - "커서, 표시"
  - "enhanced metafiles"
  - "enhanced metafiles, 표시"
  - "아이콘, 표시"
  - "static controls"
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CStatic Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정적 Windows 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CStatic : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CStatic::CStatic](../Topic/CStatic::CStatic.md)|`CStatic` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStatic::Create](../Topic/CStatic::Create.md)|Windows 정적 컨트롤을 만들고이에 연결 된 `CStatic` 개체입니다.|  
|[CStatic::DrawItem](../Topic/CStatic::DrawItem.md)|소유자가 그린 정적 컨트롤 그리기를 재정의 합니다.|  
|[CStatic::GetBitmap](../Topic/CStatic::GetBitmap.md)|이전에 설정 된 비트맵에 대 한 핸들 검색  [SetBitmap](../Topic/CStatic::SetBitmap.md).|  
|[CStatic::GetCursor](../Topic/CStatic::GetCursor.md)|커서 이미지의 핸들을 이전에 설정한 함께 검색  [SetCursor](../Topic/CStatic::SetCursor.md).|  
|[CStatic::GetEnhMetaFile](../Topic/CStatic::GetEnhMetaFile.md)|확장된 메타 파일을 이전에 설정에 대 한 핸들 검색  [SetEnhMetaFile](../Topic/CStatic::SetEnhMetaFile.md).|  
|[CStatic::GetIcon](../Topic/CStatic::GetIcon.md)|이전에 설정 아이콘의 핸들을 검색 합니다.  [SetIcon](../Topic/CStatic::SetIcon.md).|  
|[CStatic::SetBitmap](../Topic/CStatic::SetBitmap.md)|정적 컨트롤에 표시 되는 비트맵을 지정 합니다.|  
|[CStatic::SetCursor](../Topic/CStatic::SetCursor.md)|정적 컨트롤에 표시 되는 커서 이미지를 지정 합니다.|  
|[CStatic::SetEnhMetaFile](../Topic/CStatic::SetEnhMetaFile.md)|정적 컨트롤에 표시 되는 향상 된 메타 파일을 지정 합니다.|  
|[CStatic::SetIcon](../Topic/CStatic::SetIcon.md)|정적 컨트롤에 표시 될 아이콘을 지정 합니다.|  
  
## 설명  
 정적 컨트롤은 텍스트 문자열, 상자, 사각형, 아이콘, 커서, 비트맵 또는 확장된 메타 파일을 표시합니다.  레이블, 상자 또는 다른 컨트롤을 구분 하 여 사용할 수 있습니다.  일반적으로 정적 컨트롤 입력 가져와 없습니다 출력 제공. 그러나 만든 경우이 마우스 클릭의 부모 알릴 수 있습니다  **ss\_notify 호출** 스타일입니다.  
  
 정적 컨트롤의 두 단계를 만듭니다.  먼저 생성 하는 생성자를 호출의 `CStatic` 개체를 호출 하 고는  [만들기](../Topic/CStatic::Create.md) 멤버 함수는 정적 컨트롤을 만들고 연결할 수는 `CStatic` 개체.  
  
 만들 경우는 `CStatic` 대화 상자 \(대화 상자 리소스\)를 통해 개체의 `CStatic` 개체 대화 상자를 닫으면 자동으로 소멸.  
  
 만들 경우는 `CStatic` 해야 파괴 하는 창 내의 개체입니다.  A `CStatic` 스택 창 내의 개체를 자동으로 소멸 됩니다.  만들 경우는 `CStatic` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** 에서 개체 삭제를 마쳤으면.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)