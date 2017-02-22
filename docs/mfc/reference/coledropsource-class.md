---
title: "COleDropSource Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDropSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropSource class"
  - "끌어서 놓기, drop source"
  - "끌기 작업"
  - "drop target, dragging data to"
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleDropSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터가 놓기 대상으로 끌 수 있습니다.  
  
## 구문  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDropSource::COleDropSource](../Topic/COleDropSource::COleDropSource.md)|`COleDropSource` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDropSource::GiveFeedback](../Topic/COleDropSource::GiveFeedback.md)|끌어서 놓기 작업 중에 커서를 변경합니다.|  
|[COleDropSource::OnBeginDrag](../Topic/COleDropSource::OnBeginDrag.md)|마우스 캡처는 끌어서 놓기 작업 동안 처리합니다.|  
|[COleDropSource::QueryContinueDrag](../Topic/COleDropSource::QueryContinueDrag.md)|드래그 하는 검사를 계속 해야 합니다.|  
  
## 설명  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md) 클래스 수신 영역을 끌어서 놓기 작업을 처리 합니다.  `COleDropSource` 개체인 경우 끌기 작업을 시작을 결정 끌기 작업 동안 피드백을 제공 하 고 결정 하면 끌기 작업이 끝납니다.  
  
 사용 하는 `COleDropSource` 개체, 생성자를 호출 하기만 하면 됩니다.  이 마우스 클릭과 같은 이벤트를 사용 하 여 끌기 작업을 시작을 결정 하는 프로세스를 단순화할 수  [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md),  [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md), 또는  [COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md) 함수입니다.  이러한 함수를 만들 수 있는 `COleDropSource` 개체를.  기본 동작을 수정 하려는 `COleDropSource` 함수를 재정의할 수 있습니다.  이러한 멤버 함수는 적절 한 시기에 프레임 워크에 의해 호출 됩니다.  
  
 끌어서 놓기 작업에 대 한 자세한 내용은 OLE를 사용 하 여 문서를 참고 하십시오  [끌어서 놓기 \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
 자세한 내용은  [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 샘플 HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC OCLIENT 샘플](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)