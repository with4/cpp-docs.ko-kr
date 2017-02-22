---
title: "CMemoryState Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemoryState structure"
  - "메모리 누수 탐지"
  - "메모리 누수, 검색"
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CMemoryState Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램에서 메모리 누수를 검색 하는 편리한 방법을 제공 합니다.  
  
## 구문  
  
```  
struct CMemoryState  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMemoryState::CMemoryState](../Topic/CMemoryState::CMemoryState.md)|검사점 메모리 제어는 클래스와 유사한 구조를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMemoryState::Checkpoint](../Topic/CMemoryState::Checkpoint.md)|현재 메모리 상태 스냅샷을 \(검사점\)를 가져옵니다.|  
|[CMemoryState::Difference](../Topic/CMemoryState::Difference.md)|두 형식의 개체 간의 차이 계산 `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md)|이전 검사점 이후에 요약 현재 할당 된 모든 개체를 덤프합니다.|  
|[CMemoryState::DumpStatistics](../Topic/CMemoryState::DumpStatistics.md)|인쇄에 대 한 메모리 할당 통계는 `CMemoryState` 개체입니다.|  
  
## 설명  
 `CMemoryState`구조 이며는 기본 클래스가 없습니다.  
  
 메모리 개체에 대 한 힙에 할당 되지만 더 이상 필요 하지 않으면 할당 되지 때 "메모리 누수"를 발생 합니다.  이러한 메모리 누수는 결국 메모리 부족 오류를 일으킬 수 있습니다.  여러 가지 방법으로 할당 하 고 프로그램에서 메모리를 할당 합니다.  
  
-   사용 하는 `malloc`\/**사용 가능한** 제품군에서 런타임 라이브러리 함수.  
  
-   메모리 관리 Windows API 함수를 사용 하 여  **LocalAlloc**\/**LocalFree** 및  **GlobalAlloc**\/**GlobalFree**.  
  
-   C \+ \+를 사용 하 여  **새** 및  **삭제** 연산자.  
  
 `CMemoryState` 진단 하는 데 도움이 메모리 검색만 사용 하 여 메모리를 할당 하는 경우에 발생 하는 누수는  **새** 를 사용 하 여 연산자 할당 되지 않습니다  **삭제**.  비 C\+\+ 프로그램 및 혼합 된 두 그룹의 메모리 관리 함수는  **새** 및  **삭제** 같은 프로그램에서 권장 되지 않습니다.  추가 매크로 `DEBUG_NEW`, 바꾸려면 제공 되는  **새** 파일 및 줄 번호 추적 메모리를 할당 해야 하는 경우 연산자.  `DEBUG_NEW`일반적으로 사용 하는 때마다 사용 되는  **새** 연산자.  
  
 다른 진단 때에 `CMemoryState` 진단 프로그램의 디버그 버전에서 사용할 수 있습니다만.  디버그 버전이 있어야는  **\_DEBUG** 상수를 정의 합니다.  
  
 프로그램에서 메모리 누수가 있는 것으로 의심 되는 경우 사용할 수 있습니다는 `Checkpoint`,  **차이**, 및 `DumpStatistics` 함수를 두 개의 다른 지점에서 프로그램 실행 메모리 상태 \(할당 된 개체\)의 차이 검색 합니다.  이 정보는 함수를 할당 하는 모든 개체를 정리 하 고 있는지 여부를 결정 하는 유용할 수 있습니다.  
  
 단순히 할당 및 할당 취소는 불균형이 발생 하는 위치 정보를 충분히 제공 하지 않으면 사용할 수 있는 `DumpAllObjectsSince` 이후 이전 호출에 할당 된 모든 개체를 덤프 하는 함수 `Checkpoint`.  이 덤프 할당, 소스 파일 및 줄 개체가 할당 된 순서를 보여 줍니다 \(사용 하는 경우 `DEBUG_NEW` 할당에 대 한\), 및 파생 개체, 해당 주소와 크기.  `DumpAllObjectsSince`또한 각 개체의 호출 `Dump` 의 현재 상태에 대 한 정보를 제공 하는 함수입니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CMemoryState` 및 기타 진단을 참조 하십시오.  [MFC 응용 프로그램 디버깅](../Topic/MFC%20Debugging%20Techniques.md).  
  
> [!NOTE]
>  선언 형식의 개체 `CMemoryState` 및 대괄호로 멤버 함수를 호출 해야 될 묶지 여 `#if defined(_DEBUG)/#endif` 지시문입니다.  그러면 메모리 진단 프로그램의 빌드를 디버깅에 포함 될 수 있습니다.  
  
## 상속 계층 구조  
 `CMemoryState`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)