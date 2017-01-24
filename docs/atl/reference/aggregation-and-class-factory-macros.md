---
title: "Aggregation and Class Factory Macros | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], ATL macros"
  - "class factories, ATL macros"
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Aggregation and Class Factory Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 매크로는 팩토리 클래스를 선언 하 고 집계를 제어 방법을 제공 합니다.  
  
|||  
|-|-|  
|[DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)|개체 수를 선언 \(기본값\)를 집계 합니다.|  
|[DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)|선언 하는 클래스 팩터리  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), 기본 ATL 클래스 팩터리입니다.|  
|[DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md)|하는 클래스 팩터리를 클래스 팩터리 개체를 선언 합니다.|  
|[DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)|선언  [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 으로 클래스 팩터리입니다.|  
|[DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)|선언  [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 으로 클래스 팩터리입니다.|  
|[DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)|선언  [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) 으로 클래스 팩터리입니다.|  
|[DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md)|가상 선언 `GetControllingUnknown` 함수입니다.|  
|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|개체를 집계할 수 있음을 선언 합니다.|  
|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|선언 하면 개체가 반드시 집계 되도록 해야 합니다.|  
|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|알 수 없는 외부 값을 확인 하 고 집계 가능한 또는 집계 가능하지 않은, 적절 하 게 개체를 선언 합니다.|  
|[DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md)|외부 개체가 내부 개체의 생성 되는 동안 삭제에서 보호 됩니다.|  
|[DECLARE\_VIEW\_STATUS](../Topic/DECLARE_VIEW_STATUS.md)|지정 된  **상태 보기** 플래그의 컨테이너.|  
  
## 참고 항목  
 [Macros](../../atl/reference/atl-macros.md)