---
title: "Current Time: General Purpose Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "현재 시간, CTime object"
  - "개체 초기화, with the current time"
  - "프로시저, getting current time"
  - "시간, getting current"
  - "시간, setting current"
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Current Time: General Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 프로시저를 만드는 방법을 보여 줍니다 있는 `CTime` 개체와 현재 시간으로 초기화 합니다.  
  
#### 현재 시간을 가져올 수  
  
1.  할당 된 `CTime` 다음과 같은 개체:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  초기화 되지 않은 `CTime` 개체가 초기화 유효한 시간이 없습니다.  
  
2.  호출의 `CTime::GetCurrentTime` 함수를 운영 체제에서 현재 시간을 가져올 수 있습니다.  이 함수에서 반환 된 `CTime` 개체의 값을 설정 하는 데 사용할 수 `CTime`, 다음과 같이:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_2.cpp)]  
  
     이후 `GetCurrentTime` 에서 정적 멤버 함수는 `CTime` 클래스 이름이 범위 결정 연산자는 클래스의 이름을 한 정해야 합니다 \(`::`\), `CTime::GetCurrentTime()`.  
  
 물론 두 단계 이전에 단일 프로그램 문으로 같이 결합 될 수 있습니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_3.cpp)]  
  
## 참고 항목  
 [Date and Time: General\-Purpose Classes](../atl-mfc-shared/date-and-time-general-purpose-classes.md)