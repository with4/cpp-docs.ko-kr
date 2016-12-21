---
title: "CJumpList Class | Microsoft Docs"
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
  - "afxadv/CJumpList"
  - "CJumpList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CJumpList class"
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CJumpList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A `CJumpList` 바로 가기 아이콘이 작업 표시줄에서 마우스 오른쪽 단추로 클릭 하면 표시 목록입니다.  
  
## 구문  
  
```  
class CJumpList;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CJumpList::CJumpList](../Topic/CJumpList::CJumpList.md)|`CJumpList` 개체를 생성합니다.|  
|[CJumpList::~CJumpList](../Topic/CJumpList::~CJumpList.md)|`CJumpList` 개체를 소멸시킵니다.|  
  
|Name|설명|  
|----------|--------|  
|[CJumpList::AbortList](../Topic/CJumpList::AbortList.md)|건물 목록 트랜잭션을 커밋하지 않고 중단합니다.|  
|[CJumpList::AddDestination](../Topic/CJumpList::AddDestination.md)|오버로드.  대상 목록에 추가합니다.|  
|[CJumpList::AddKnownCategory](../Topic/CJumpList::AddKnownCategory.md)|알려진 범주 목록에 추가합니다.|  
|[CJumpList::AddTask](../Topic/CJumpList::AddTask.md)|오버로드.  정식 작업 범주에 항목을 추가합니다.|  
|[CJumpList::AddTasks](../Topic/CJumpList::AddTasks.md)|정식 작업 범주에 항목을 추가합니다.|  
|[CJumpList::AddTaskSeparator](../Topic/CJumpList::AddTaskSeparator.md)|작업 사이 구분 기호를 추가합니다.|  
|[CJumpList::ClearAll](../Topic/CJumpList::ClearAll.md)|제거 작업 및 대상의 현재 인스턴스를 추가한 모든 `CJumpList` 지금까지.|  
|[CJumpList::ClearAllDestinations](../Topic/CJumpList::ClearAllDestinations.md)|현재 인스턴스를 추가한 모든 대상을 제거 `CJumpList` 지금까지.|  
|[CJumpList::CommitList](../Topic/CJumpList::CommitList.md)|건물 목록 트랜잭션을 종료 하 고 보고 된 목록에 연결 된 저장소 \(이 경우 레지스트리.\) 적용|  
|[CJumpList::GetDestinationList](../Topic/CJumpList::GetDestinationList.md)|대상 목록에 대 한 인터페이스 포인터를 검색합니다.|  
|[CJumpList::GetMaxSlots](../Topic/CJumpList::GetMaxSlots.md)|호출 응용 프로그램의 대상 메뉴에서 표시할 수 있는 범주 머리글을 포함 하 여 항목의 최대 수를 검색 합니다.|  
|[CJumpList::GetRemovedItems](../Topic/CJumpList::GetRemovedItems.md)|반환 배열을 나타내는 항목의 대상을 제거 합니다.|  
|[CJumpList::InitializeList](../Topic/CJumpList::InitializeList.md)|건물 목록 트랜잭션을 시작합니다.|  
|[CJumpList::SetAppID](../Topic/CJumpList::SetAppID.md)|빌드되는 목록에 대 한 사용자 모델 응용 프로그램 ID를 설정 합니다.|  
  
## 상속 계층 구조  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## 요구 사항  
 **헤더:**  afxadv.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)