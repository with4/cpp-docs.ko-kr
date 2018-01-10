---
title: '&lt;tuple&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <tuple>
dev_langs: C++
helpviewer_keywords: tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ca10e245c4adf108799896b8dfad2e21c4f3758
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="lttuplegt"></a>&lt;tuple&gt;
해당 인스턴스에 다양한 형식의 개체가 포함된 `tuple` 템플릿을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[tuple](../standard-library/tuple-class.md)|고정 길이의 요소 시퀀스를 래핑합니다.|  
|[tuple_element 클래스](../standard-library/tuple-element-class-tuple.md)|`tuple` 요소의 형식을 래핑합니다.|  
|[tuple_size 클래스](../standard-library/tuple-size-class-tuple.md)|`tuple` 요소 개수를 래핑합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|`tuple` 개체 비교, 같음|  
|[operator!=](../standard-library/tuple-operators.md#op_neq)|`tuple` 개체 비교, 같지 않음|  
|[operator<](../standard-library/tuple-operators.md#op_lt)|`tuple` 개체 비교, 더 작음|  
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|`tuple` 개체 비교, 작거나 같음|  
|[operator>](../standard-library/tuple-operators.md#op_gt)|`tuple` 개체 비교, 더 큼|  
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|`tuple` 개체 비교, 크거나 같음|  
  
### <a name="functions"></a>함수  
  
|||  
|-|-|  
|[get](../standard-library/tuple-functions.md#get)|`tuple` 개체에서 요소를 가져옵니다.|  
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|요소 값에서 `tuple`을 만듭니다.|  
|[tie](../standard-library/tuple-functions.md#tie)|요소 선언에서 `tuple`을 만듭니다.|  
  
## <a name="see-also"></a>참고 항목  
 [\<array>](../standard-library/array.md)

