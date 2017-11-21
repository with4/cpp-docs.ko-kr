---
title: "기본 클래스 팩터리와 집계 모델 변경 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a963c1fba2d3eda9c86fa1e6db74de739bf45182
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>기본 클래스 팩터리와 집계 모델 변경
ATL 사용 하 여 [CComCoClass](../atl/reference/ccomcoclass-class.md) 개체에 대 한 기본 클래스 팩터리와 집계 모델을 정의할 수 있습니다. `CComCoClass`다음 두 매크로 지정합니다.  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) 되려면 클래스 팩터리 선언 [CComClassFactory](../atl/reference/ccomclassfactory-class.md)합니다.  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) 개체를 집계할 수 있도록 선언 합니다.  
  
 클래스 정의에서 다른 매크로 지정 하 여 이러한 기본값 중 하나를 재정의할 수 있습니다. 예를 들어, 사용 하도록 [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) 대신 `CComClassFactory`, 지정 된 [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) 매크로:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 클래스 팩터리를 정의 하는 다른 두 매크로 [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 및 [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton)합니다.  
  
 ATL 또한 사용 하 여는 `typedef` 기본 동작을 구현 하는 메커니즘입니다. 예를 들어는 `DECLARE_AGGREGATABLE` 사용 하 여 매크로 `typedef` 호출 형식을 정의 하려면 **_CreatorClass**, 다음 ATL. 전반에 걸쳐 되는 파생된 클래스에서는 `typedef` 기본 클래스와 동일한 이름을 사용 하 여 `typedef` atl 프로그램 정의 사용 하 고 기본 동작 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md)   
 [집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)

