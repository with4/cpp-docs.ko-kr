---
title: "CMFCTasksPaneTask Class | Microsoft Docs"
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
  - "CMFCTasksPaneTask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTask class"
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTasksPaneTask Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCTasksPaneTask` 클래스는 작업을 작업 창 컨트롤에 대 한 도우미 클래스 \([CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)\).  작업 개체의 작업 그룹에서 항목을 나타냅니다 \([CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\).  각 작업은 작업 및 작업 이름 왼쪽에 표시 되는 아이콘을 클릭할 때 프레임 워크를 실행 하는 명령을 수 있습니다.  
  
## 구문  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](../Topic/CMFCTasksPaneTask::CMFCTasksPaneTask.md)|`CMFCTasksPaneTask` 개체를 만들어 초기화합니다.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCTasksPaneTask::SetACCData](../Topic/CMFCTasksPaneTask::SetACCData.md)|현재 작업에 대 한 내게 필요한 옵션 데이터를 결정합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCTasksPaneTask::m\_bAutoDestroyWindow](../Topic/CMFCTasksPaneTask::m_bAutoDestroyWindow.md)|작업 창이 자동으로 소멸 됩니다 여부를 결정 합니다.|  
|[CMFCTasksPaneTask::m\_bIsBold](../Topic/CMFCTasksPaneTask::m_bIsBold.md)|프레임 워크 작업 레이블을 굵은 텍스트를 그릴지 여부를 결정 합니다.|  
|[CMFCTasksPaneTask::m\_dwUserData](../Topic/CMFCTasksPaneTask::m_dwUserData.md)|프레임 워크 작업을 연결 하는 사용자 정의 데이터를 포함 합니다.  작업에 연결 된 데이터가 없는 경우 0으로 설정 합니다.|  
|[CMFCTasksPaneTask::m\_hwndTask](../Topic/CMFCTasksPaneTask::m_hwndTask.md)|작업 창에 대 한 핸들입니다.|  
|[CMFCTasksPaneTask::m\_nIcon](../Topic/CMFCTasksPaneTask::m_nIcon.md)|프레임 워크 작업 옆에 표시 되는 이미지의 이미지 목록에서 인덱스입니다.|  
|[CMFCTasksPaneTask::m\_nWindowHeight](../Topic/CMFCTasksPaneTask::m_nWindowHeight.md)|작업 창의 높이 지정 합니다.  작업 창 없음 작업 있는 경우이 값은 0입니다.|  
|[CMFCTasksPaneTask::m\_pGroup](../Topic/CMFCTasksPaneTask::m_pGroup.md)|에 대 한 포인터는 `CMFCTasksPaneTaskGroup` 이 작업에 속한.|  
|[CMFCTasksPaneTask::m\_rect](../Topic/CMFCTasksPaneTask::m_rect.md)|작업의 경계 사각형을 지정합니다.|  
|[CMFCTasksPaneTask::m\_strName](../Topic/CMFCTasksPaneTask::m_strName.md)|작업의 이름입니다.|  
|[CMFCTasksPaneTask::m\_uiCommandID](../Topic/CMFCTasksPaneTask::m_uiCommandID.md)|작업을 두 번 클릭할 때 프레임 워크를 실행 하는 명령 명령 ID를 지정 합니다.  유효한 명령 ID이 값이 없으면 작업 간단한 레이블로 처리 됩니다.|  
  
## 설명  
 다음 그림 3 작업 포함 된 작업 그룹을 보여 줍니다.  
  
 ![작업 그룹, 확장됨](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
> [!NOTE]
>  유효한 명령 ID는 작업 하지 않은 경우 간단한 레이블로 처리 됩니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## 요구 사항  
 **헤더:** afxTasksPane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)