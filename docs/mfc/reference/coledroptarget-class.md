---
title: "COleDropTarget Class | Microsoft Docs"
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
  - "COleDropTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropTarget class"
  - "끌어서 놓기, drop target"
  - "drop commands"
  - "drop commands, 수락"
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDropTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 라이브러리 창 사이의 통신 메커니즘을 제공합니다.  
  
## 구문  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDropTarget::COleDropTarget](../Topic/COleDropTarget::COleDropTarget.md)|`COleDropTarget` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDropTarget::OnDragEnter](../Topic/COleDropTarget::OnDragEnter.md)|커서는 창을 처음 들어가면 호출 됩니다.|  
|[COleDropTarget::OnDragLeave](../Topic/COleDropTarget::OnDragLeave.md)|커서 창 밖으로 끌 때 호출 됩니다.|  
|[COleDropTarget::OnDragOver](../Topic/COleDropTarget::OnDragOver.md)|창 위에 커서를 끌 때 반복적으로 호출 합니다.|  
|[COleDropTarget::OnDragScroll](../Topic/COleDropTarget::OnDragScroll.md)|호출 창 스크롤 영역에 커서를 끌 여부를 확인 합니다.|  
|[COleDropTarget::OnDrop](../Topic/COleDropTarget::OnDrop.md)|데이터 창에서 기본 처리기를 놓을 때 호출 됩니다.|  
|[COleDropTarget::OnDropEx](../Topic/COleDropTarget::OnDropEx.md)|데이터 창에서 초기 처리기를 놓을 때 호출 됩니다.|  
|[COleDropTarget::Register](../Topic/COleDropTarget::Register.md)|창의 유효한 놓기 대상으로 등록합니다.|  
|[COleDropTarget::Revoke](../Topic/COleDropTarget::Revoke.md)|중단 되는 유효한 놓기 대상 창이 됩니다.|  
  
## 설명  
 이 클래스의 개체를 만드는 창을 OLE 끌어서 놓기 메커니즘을 통해 데이터를 받을 수 있습니다.  
  
 Drop 명령을 수락 창이 나타나도록 하려면 먼저 개체를 만들어야 합니다의 `COleDropTarget` 클래스 및 다음 호출의  [등록](../Topic/COleDropTarget::Register.md) 원하는에 대 한 포인터가 함수 `CWnd` 객체를 유일한 매개 변수로.  
  
 끌어서 놓기 작업에 대 한 자세한 내용은 OLE를 사용 하 여 문서를 참고 하십시오  [끌어서 놓기 \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 샘플 HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC OCLIENT 샘플](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDropSource Class](../../mfc/reference/coledropsource-class.md)