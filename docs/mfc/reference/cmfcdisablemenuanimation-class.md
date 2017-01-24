---
title: "CMFCDisableMenuAnimation Class | Microsoft Docs"
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
  - "CMFCDisableMenuAnimation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDisableMenuAnimation class"
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDisableMenuAnimation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

팝업 메뉴 애니메이션을 사용 하지 않습니다.  
  
## 구문  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` 개체를 생성합니다.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCDisableMenuAnimation::Restore](../Topic/CMFCDisableMenuAnimation::Restore.md)|팝업 메뉴를 표시 하는 프레임 워크를 사용 하는 이전 애니메이션을 복원 합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCDisableMenuAnimation::m_animType`|이전 팝업 메뉴 애니메이션 형식으로 저장합니다.|  
  
### 설명  
 이 도우미 클래스 팝업 메뉴 애니메이션 \(예: 마우스 또는 키보드 명령을 처리 하는 경우\) 일시적으로 사용 합니다.  
  
 A `CMFCDisableMenuAnimation` 개체 수명 동안 팝업 메뉴 애니메이션을 사용 하지 않습니다.  현재 애니메이션 형식 팝업 메뉴에서 생성자 저장 된 `m_animType` 집합 현재 애니메이션을 입력 하 고 필드 `CMFCPopupMenu::NO_ANIMATION`.  소멸자가 이전 애니메이션 형식을 복원합니다.  
  
 만들 수 있는 `CMFCDisableMenuAnimation` 스택 전반에 걸쳐 단일 함수 팝업 메뉴 애니메이션을 사용 하지 않으려면 개체.  사이의 함수 팝업 메뉴 애니메이션을 사용 하지 않으려는 경우 만들기를 `CMFCDisableMenuAnimation` 힙에 개체 및 팝업 메뉴 애니메이션을 복원 하려는 경우 삭제 합니다.  
  
## 예제  
 다음 예제에서는 애니메이션 메뉴를 임시로 비활성화 하려면 스택을 사용 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/CPP/cmfcdisablemenuanimation-class_1.h)]  
  
## 상속 계층 구조  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## 요구 사항  
 **헤더:** afxpopupmenu.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)