---
title: "CRectTracker Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRectTracker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRectTracker class"
  - "displaying items"
  - "resizing items"
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRectTracker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

항목을 표시, 이동, 및 다른 이성적으로 크기를 조정할 수 있습니다.  
  
## 구문  
  
```  
  
class CRectTracker  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRectTracker::CRectTracker](../Topic/CRectTracker::CRectTracker.md)|`CRectTracker` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRectTracker::AdjustRect](../Topic/CRectTracker::AdjustRect.md)|사각형의 크기를 조정할 때 호출 됩니다.|  
|[CRectTracker::Draw](../Topic/CRectTracker::Draw.md)|사각형을 렌더링합니다.|  
|[CRectTracker::DrawTrackerRect](../Topic/CRectTracker::DrawTrackerRect.md)|테두리를 그릴 때 호출 된 `CRectTracker` 개체입니다.|  
|[CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)|마스크를 가져오기 위해 호출을 `CRectTracker`항목의 크기 조정 핸들입니다.|  
|[CRectTracker::GetTrueRect](../Topic/CRectTracker::GetTrueRect.md)|크기 조정 핸들을 포함 하 여 사각형의 너비와 높이 반환 합니다.|  
|[CRectTracker::HitTest](../Topic/CRectTracker::HitTest.md)|반환 관련 커서의 현재 위치는 `CRectTracker` 개체.|  
|[CRectTracker::NormalizeHit](../Topic/CRectTracker::NormalizeHit.md)|적중 테스트 코드를 정규화합니다.|  
|[CRectTracker::OnChangedRect](../Topic/CRectTracker::OnChangedRect.md)|사각형의 크기를 조정 하거나 이동 하면 호출 됩니다.|  
|[CRectTracker::SetCursor](../Topic/CRectTracker::SetCursor.md)|위에 사각형의 위치에 따라 커서를 설정합니다.|  
|[CRectTracker::Track](../Topic/CRectTracker::Track.md)|사각형을 조작할 수 있습니다.|  
|[CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md)|"고무 밴드" 사용자가 선택할 수 있습니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CRectTracker::m\_nHandleSize](../Topic/CRectTracker::m_nHandleSize.md)|크기 조정 핸들의 크기를 결정합니다.|  
|[CRectTracker::m\_nStyle](../Topic/CRectTracker::m_nStyle.md)|현재 style\(s\) 추적기입니다.|  
|[CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md)|현재 위치 \(픽셀\)의 사각형입니다.|  
|[CRectTracker::m\_sizeMin](../Topic/CRectTracker::m_sizeMin.md)|최소 사각형의 너비와 높이 결정합니다.|  
  
## 설명  
 `CRectTracker`기본 클래스에 없는 것입니다.  
  
 하지만 `CRectTracker` 클래스는 그래픽 인터페이스를 사용 하 여 OLE 항목과 상호 작용할 수 있도록 설계 되었습니다, 그 사용 OLE 지원 응용 프로그램에 제한 되지 않습니다.  사용할 수 있는 곳 이나 사용자 인터페이스입니다.  
  
 `CRectTracker`테두리는 실선 수 또는 점선.  항목 항목의 여러 상태를 나타내는 빗살된 무늬로 중첩 하거나 빗금 테두리가 있습니다.  외부 또는 내부에 8 개의 크기 조정 핸들을 배치할 수 있습니다 항목의 테두리.  \(크기 조정 핸들에 대 한 설명은 참조 하십시오.  [GetHandleMask](../Topic/CRectTracker::GetHandleMask.md).\) 마지막으로 `CRectTracker` 항목의 크기를 조정 하는 동안 방향을 변경할 수 있습니다.  
  
 사용할 `CRectTracker`, 생성는 `CRectTracker` 개체와 지정 디스플레이 상태는 초기화 됩니다.  이 인터페이스와 연결 된 OLE 항목의 현재 상태는 사용자가 시각적 피드백을 제공 수 있는 `CRectTracker` 개체입니다.  
  
 사용에 대 한 자세한 내용은 `CRectTracker`, 문서를 참조 하십시오.  [추적기](../../mfc/trackers.md).  
  
## 상속 계층 구조  
 `CRectTracker`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [MFC 샘플 추적기](../../top/visual-cpp-samples.md)   
 [MFC DRAWCLI 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleResizeBar Class](../../mfc/reference/coleresizebar-class.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)