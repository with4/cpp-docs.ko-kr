---
title: "CMenuTearOffManager Class | Microsoft Docs"
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
  - "CMenuTearOffManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenuTearOffManager class"
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMenuTearOffManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

분리 된 메뉴를 관리합니다.  분리 된 메뉴를 메뉴 모음의 메뉴입니다.  사용자 메뉴 모음, 부동 소수점으로 분리 된 메뉴를 일으키는 분리 된 메뉴를 제거할 수 있습니다.  
  
## 구문  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMenuTearOffManager::CMenuTearOffManager](../Topic/CMenuTearOffManager::CMenuTearOffManager.md)|`CMenuTearOffManager` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMenuTearOffManager::Build](../Topic/CMenuTearOffManager::Build.md)||  
|[CMenuTearOffManager::GetRegPath](../Topic/CMenuTearOffManager::GetRegPath.md)||  
|[CMenuTearOffManager::Initialize](../Topic/CMenuTearOffManager::Initialize.md)|`CMenuTearOffManager` 개체를 초기화합니다.|  
|[CMenuTearOffManager::IsDynamicID](../Topic/CMenuTearOffManager::IsDynamicID.md)||  
|[CMenuTearOffManager::Parse](../Topic/CMenuTearOffManager::Parse.md)||  
|[CMenuTearOffManager::Reset](../Topic/CMenuTearOffManager::Reset.md)||  
|[CMenuTearOffManager::SetInUse](../Topic/CMenuTearOffManager::SetInUse.md)||  
|[CMenuTearOffManager::SetupTearOffMenus](../Topic/CMenuTearOffManager::SetupTearOffMenus.md)||  
  
## 설명  
 응용 프로그램에서 분리 된 메뉴를 사용 하려면 해야는 `CMenuTearOffManager` 개체입니다.  대부분의 경우 초기화 하거나 없습니다 만들기는 `CMenuTearOffManager` 개체를 직접.  전화를 할 경우이 처리 되는 [CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md) 함수.  
  
## 예제  
 생성 하 고 초기화 하는 방법 다음 예제는 `CMenuTearOffManager` 를 호출 하 여 개체의 `CWinAppEX::EnableTearOffMenus` 메서드.  이 코드 조각에 속해 있는  [워드 패드 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/CPP/cmenutearoffmanager-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxmenutearoffmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)