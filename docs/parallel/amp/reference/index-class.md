---
title: "index 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "index 구조체"
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# index 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

*N*차원 인덱스 포인트를 정의합니다.  
  
## 구문  
  
```  
template <  
   int _Rank  
>  
class index;  
```  
  
#### 매개 변수  
 `_Rank`  
 차원의 순위 또는 번호입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[index::index 생성자](../Topic/index::index%20Constructor.md)|`index` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[index::operator\-\- 연산자](../Topic/index::operator--%20Operator.md)|`index` 개체의 각 요소를 감소시킵니다.|  
|[index::operator\(mod\)\= 연산자](../Topic/index::operator\(mod\)=%20Operator.md)|`index` 개체의 각 요소를 숫자로 나눌 때의 나머지를 계산합니다.|  
|[index::operator\*\= 연산자](../Topic/index::operator*=%20Operator.md)|`index` 개체의 각 요소에 숫자를 곱합니다.|  
|[index::operator\/\= 연산자](../Topic/index::operator-=%20Operator2.md)|숫자로 `index` 개체의 각 요소를 나눕니다.|  
|[index::operatorOperator](../Topic/index::operatorOperator.md)|지정된 인덱스에 있는 요소를 반환합니다.|  
|[index::operator\+\+ 연산자](../Topic/index::operator++%20Operator.md)|`index` 개체의 각 요소를 증가시킵니다.|  
|[index::operator\+\= 연산자](../Topic/index::operator+=%20Operator.md)|`index` 개체의 각 요소에 지정한 수를 추가합니다.|  
|[index::operator\= 연산자](../Topic/index::operator=%20Operator.md)|지정된 `index` 개체의 내용을 여기로 복사합니다.|  
|[index::operator\-\= 연산자](../Topic/index::operator-=%20Operator1.md)|`index` 개체의 각 요소에서 지정한 수를 뺍니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[index::rank 상수](../Topic/index::rank%20Constant.md)|`index` 개체의 순위를 저장합니다.|  
  
## 상속 계층  
 `index`  
  
## 설명  
 `index` 구조체는 *N*차원 공간에서 고유 위치를 지정하는 *N* 정수의 좌표 백터를 나타냅니다.  벡터 값은 최상위에서 최하위 순서로 정렬됩니다.  [index::operator\= 연산자](../Topic/index::operator=%20Operator.md)를 사용해서 구성 요소 값을 검색할 수 있습니다.  
  
## 요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)