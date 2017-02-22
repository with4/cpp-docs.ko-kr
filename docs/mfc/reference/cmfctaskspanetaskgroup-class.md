---
title: "CMFCTasksPaneTaskGroup Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPaneTaskGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTaskGroup class"
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTasksPaneTaskGroup Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCTasksPaneTaskGroup` 클래스에서 사용 되는 도우미 클래스입니다는  [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 제어 합니다.  개체 형식의 `CMFCTasksPaneTaskGroup` 표시는  *작업 그룹*.  작업 그룹 프레임 워크 축소 단추가 있는 별도 상자에 표시 되는 항목의 목록입니다.  상자 \(그룹 이름\) 캡션을 넣을 수 있습니다.  그룹을 축소 하는 경우 작업 목록에 표시 되지 않습니다.  
  
## 구문  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](../Topic/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup.md)|`CMFCTasksPaneTaskGroup` 개체를 생성합니다.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCTasksPaneTaskGroup::SetACCData](../Topic/CMFCTasksPaneTaskGroup::SetACCData.md)|현재 작업 그룹에 대 한 내게 필요한 옵션 데이터를 결정합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCTasksPaneTaskGroup::m\_bIsBottom](../Topic/CMFCTasksPaneTaskGroup::m_bIsBottom.md)|작업 그룹을 작업 창 컨트롤의 아래쪽으로 정렬할지 여부를 결정 합니다.|  
|[CMFCTasksPaneTaskGroup::m\_bIsCollapsed](../Topic/CMFCTasksPaneTaskGroup::m_bIsCollapsed.md)|작업 그룹 축소 되는지 여부를 결정 합니다.|  
|[CMFCTasksPaneTaskGroup::m\_bIsSpecial](../Topic/CMFCTasksPaneTaskGroup::m_bIsSpecial.md)|작업 그룹에 있는지 여부를 확인  *특수.* 다른 색으로 특별 한 캡션을 표시 하는 프레임 워크입니다.|  
|[CMFCTasksPaneTaskGroup::m\_lstTasks](../Topic/CMFCTasksPaneTaskGroup::m_lstTasks.md)|내부 작업 목록을 포함 합니다.|  
|[CMFCTasksPaneTaskGroup::m\_rect](../Topic/CMFCTasksPaneTaskGroup::m_rect.md)|캡션은 그룹의 경계 사각형을 지정합니다.|  
|[CMFCTasksPaneTaskGroup::m\_rectGroup](../Topic/CMFCTasksPaneTaskGroup::m_rectGroup.md)|그룹의 경계 사각형을 지정합니다.|  
|[CMFCTasksPaneTaskGroup::m\_strName](../Topic/CMFCTasksPaneTaskGroup::m_strName.md)|그룹의 이름을 지정합니다.|  
  
## 설명  
 다음 그림은 확장 된 작업 그룹을 보여 줍니다.  
  
 ![작업 그룹, 확장됨](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
 다음 그림은 축소 된 작업 그룹을 보여 줍니다.  
  
 ![축소된 작업 그룹](../../mfc/reference/media/nexttaskgrpcollapse.png "NextTaskGrpCollapse")  
  
 다음 그림 캡션 없이 작업 그룹을 보여 줍니다.  
  
 ![캡션이 없는 작업 그룹](../../mfc/reference/media/nexttaskgrpnocapt.png "NextTaskGrpNoCapt")  
  
 다음 그림에서는 두 작업 그룹이 표시 됩니다.  첫 번째 작업 그룹을 설정 하 여와 특수 표시 된는 `m_bIsSpecial` 플래그 `TRUE`, 두 번째 작업 그룹 특수 상태.  첫 번째 작업 그룹에 대 한 캡션을 두 번째 작업 그룹 보다 어두운 방식을 note:  
  
 ![특수 작업 그룹](../../mfc/reference/media/nexttaskgrpspecial.png "NextTaskGrpSpecial")  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## 요구 사항  
 **헤더:** afxTasksPane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)