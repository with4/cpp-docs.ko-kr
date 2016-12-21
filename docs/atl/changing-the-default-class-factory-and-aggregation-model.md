---
title: "Changing the Default Class Factory and Aggregation Model | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "aggregation [C++], ATL 사용"
  - "CComClassFactory class, making the default"
  - "CComCoClass class, default class factory and aggregation model"
  - "class factories, 기본값 변경"
  - "default class factory"
  - "default class factory, ATL"
  - "기본값[C++], aggregation model in ATL"
  - "기본값[C++], class factory"
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Default Class Factory and Aggregation Model
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL을 사용 하 여  [CComCoClass](../atl/reference/ccomcoclass-class.md) 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 정의 합니다.  `CComCoClass`다음 두 개의 매크로 지정합니다.  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) 를 선언 하는 클래스 팩터리  [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) 개체가 집계 될 수 있도록 선언 합니다.  
  
 이러한 기본값 중 하나를 클래스 정의에 다른 매크로 지정 하 여 재정의할 수 있습니다.  사용 방법에 대 한  [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) 대신 `CComClassFactory`에서 지정 된  [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) 매크로:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/CPP/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 클래스 팩터리를 정의 하는 다른 두 매크로  [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) 및  [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md).  
  
 또한 ATL을 사용 하 여 `typedef` 기본 동작을 구현 하는 메커니즘입니다.  예를 들어,는 `DECLARE_AGGREGATABLE` 매크로 사용 하 여 `typedef` 라는 형식을 정의할 수  **\_CreatorClass**, ATL.에서 참조 되 고  이때 파생된 클래스에는 `typedef` 기본 클래스의 같은 이름으로 `typedef` 결과 정의 사용 하 여 기본 동작을 재정의 하 고 ATL에서.  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)