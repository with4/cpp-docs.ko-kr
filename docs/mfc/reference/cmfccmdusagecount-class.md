---
title: "CMFCCmdUsageCount Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCmdUsageCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCmdUsageCount class"
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCCmdUsageCount Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 항목 메뉴에서 선택할 때와 같은 Windows 메시지의 사용 횟수를 추적 합니다.  
  
## 구문  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|기본 생성자입니다.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCCmdUsageCount::AddCmd](../Topic/CMFCCmdUsageCount::AddCmd.md)|지정 된 명령과 연결 된 카운터 1 증가 합니다.|  
|[CMFCCmdUsageCount::GetCount](../Topic/CMFCCmdUsageCount::GetCount.md)|지정 된 명령 ID와 연결 된 사용 횟수를 검색 합니다.|  
|[CMFCCmdUsageCount::HasEnoughInformation](../Topic/CMFCCmdUsageCount::HasEnoughInformation.md)|이 개체 최소 양을 추적 데이터 수집 했습니다 여부를 결정 합니다.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](../Topic/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd.md)|지정 된 명령을 자주 사용 되는지 여부를 결정 합니다.|  
|[CMFCCmdUsageCount::Reset](../Topic/CMFCCmdUsageCount::Reset.md)|모든 명령 사용 횟수를 지웁니다.|  
|[CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md)|이 개체는 보관 파일에서 읽거나 아카이브 수를 씁니다.  \(재정의 [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md)|값의 집합을 공유 `CMFCCmdUsageCount` 클래스 데이터 멤버입니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|Name|설명|  
|`m_CmdUsage`|A `CMap` 개체의 사용 횟수를 명령에 매핑합니다.|  
|`m_nMinUsagePercentage`|자주 사용 되는 명령에 대 한 최소 사용 비율입니다.|  
|`m_nStartCount`|이 개체 추적 데이터의 최소 수집 했습니다 여부를 결정 하는 데 사용 되는 시작 카운터입니다.|  
|`m_nTotalUsage`|모든 변경 명령 수입니다.|  
  
### 설명  
 `CMFCCmdUsageCount` 클래스에는 32 비트 부호 없는 정수 카운터 각 숫자 Windows 메시지 식별자 매핑합니다.  `CMFCToolBar`이 클래스를 사용 하 여 자주 사용 하는 도구 모음 항목을 표시 합니다.  `CMFCToolBar`에 대한 자세한 내용은 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)를 참조하십시오.  
  
 유지할 수 있는 `CMFCCmdUsageCount` 프로그램 실행 사이의 데이터 클래스.  사용 된 [CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md) 클래스 멤버 데이터를 직렬화 하는 메서드 및 [CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md) 공유 멤버 데이터를 설정 하는 방법.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## 요구 사항  
 **헤더:** afxcmdusagecount.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)