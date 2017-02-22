---
title: "COM Map Macros | Microsoft Docs"
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
  - "COM 인터페이스, COM map macros"
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# COM Map Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 매크로 COM 인터페이스 맵을 정의합니다.  
  
|||  
|-|-|  
|[BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md)|시작 COM 인터페이스 맵 엔트리를 표시합니다.|  
|[COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20Macros.md)|인터페이스는 COM 인터페이스 맵에 들어갑니다.|  
|[COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md)|이 매크로 상속의 두 분기 사용.|  
|[COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)|이 매크로 사용 하면 인터페이스의 COM 맵에 입력 하 고 IID를 지정 합니다.|  
|[COM\_INTERFACE\_ENTRY2\_IID](../Topic/COM_INTERFACE_ENTRY2_IID.md)|동일  [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md), 제외 하 고는 다른 IID를 지정할 수 있습니다.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md)|때 표시 되는 인터페이스 `iid` 를 쿼리할 `COM_INTERFACE_ENTRY_AGGREGATE` 를 전달 `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AGGREGATE_BLIND.md)|동일  [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), 모든 IID에 대 한 쿼리 결과 쿼리를 전달에서 제외 하 고 `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md)|동일  [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), 경우 제외 `punk` 는  **NULL**, 설명 집계를 자동으로 만듭니다를 `clsid`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)|동일  [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md)모든 IID에 대 한 쿼리 결과 쿼리를 전달에서 제외 하 고, `punk`, 경우 `punk` 는  **NULL**, 자동으로 만들기로 표시 된 집계는 `clsid`.|  
|[COM\_INTERFACE\_ENTRY\_BREAK](../Topic/COM_INTERFACE_ENTRY_BREAK.md)|프로그램을 호출 하면  [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) 때 지정한 인터페이스 쿼리를.|  
|[COM\_INTERFACE\_ENTRY\_CACHED\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_CACHED_TEAR_OFF.md)|모든 인스턴스에 대 한 인터페이스 관련 데이터를 저장합니다.|  
|[COM\_INTERFACE\_ENTRY\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_TEAR_OFF.md)|분리 된 인터페이스를 노출합니다.|  
|[COM\_INTERFACE\_ENTRY\_CHAIN](../Topic/COM_INTERFACE_ENTRY_CHAIN.md)|처리 COM 구조에서이 항목에 도달 하면 기본 클래스의 COM 맵을 처리 합니다.|  
|[COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md)|ATL에 연결 하는 일반 메커니즘 `QueryInterface` 논리.|  
|[COM\_INTERFACE\_ENTRY\_FUNC\_BLIND](../Topic/COM_INTERFACE_ENTRY_FUNC_BLIND.md)|동일  [COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md)를 호출 하는 IID에 대 한 쿼리 결과 제외 하 고, `func`.|  
|[COM\_INTERFACE\_ENTRY\_NOINTERFACE](../Topic/COM_INTERFACE_ENTRY_NOINTERFACE.md)|반환  **인터페이스** 지정 된 인터페이스에 대해 쿼리할 때 COM 맵을 처리를 종료 합니다.|  
|[END\_COM\_MAP](../Topic/END_COM_MAP.md)|COM 인터페이스 맵 엔트리 끝을 표시 합니다.|  
  
## 참고 항목  
 [Macros](../../atl/reference/atl-macros.md)   
 [COM Map Global Functions](../../atl/reference/com-map-global-functions.md)