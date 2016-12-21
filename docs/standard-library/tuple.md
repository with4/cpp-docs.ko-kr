---
title: "&lt; 튜플 &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<tuple>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "튜플 헤더[TR1]"
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; 튜플 &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿을 정의 `tuple` 인스턴스가 다양 한 유형의 개체를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[튜플](../standard-library/tuple-class.md)|고정 길이의 요소 시퀀스를 래핑합니다.|  
|[tuple_element 클래스](../standard-library/tuple-element-class-tuple.md)|`tuple` 요소의 형식을 래핑합니다.|  
|[tuple_size 클래스](../standard-library/tuple-size-class-tuple.md)|`tuple` 요소 개수를 래핑합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 = =](../Topic/%3Ctuple%3E%20operators.md#operator_eq_eq)|비교 `tuple` 같은 개체|  
|[연산자! =](../Topic/%3Ctuple%3E%20operators.md#operator_neq)|비교 `tuple` 개체, 같지 않음|  
|[연산자 <](../Topic/%3Ctuple%3E%20operators.md#operator_lt_)|비교 `tuple` 개체 미만|  
|[연산자 < =](../Topic/%3Ctuple%3E%20operators.md#operator_lt__eq)|비교 `tuple` 개체 보다 작거나 같음|  
|[연산자 >](../Topic/%3Ctuple%3E%20operators.md#operator_gt_)|비교 `tuple` 보다 큰 개체|  
|[연산자 > =](../Topic/%3Ctuple%3E%20operators.md#operator_gt__eq)|비교 `tuple` 개체 보다 크거나 같음|  
  
### <a name="functions"></a>함수  
  
|||  
|-|-|  
|[가져오기](../Topic/%3Ctuple%3E%20functions.md#get_function)|`tuple` 개체에서 요소를 가져옵니다.|  
|[make_tuple](../Topic/%3Ctuple%3E%20functions.md#make_tuple_function)|사용 하면 한 `tuple` 에서 요소 값입니다.|  
|[연결](../Topic/%3Ctuple%3E%20functions.md#tie_function)|사용 하면 한 `tuple` 요소 참조에서 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [\< 배열>](../standard-library/array.md)

