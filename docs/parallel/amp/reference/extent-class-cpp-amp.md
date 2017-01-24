---
title: "extent 클래스(C++ AMP) | Microsoft Docs"
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
  - "amp/Concurrency::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent 구조체"
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# extent 클래스(C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

원점이 0인 *N*차원 공간의 경계를 지정하는 *N* 정수 값의 벡터를 나타냅니다.  벡터 값은 최상위에서 최하위 순서로 정렬됩니다.  
  
## 구문  
  
```  
template <  
   int _Rank>  
class extent;  
```  
  
#### 매개 변수  
 `_Rank`  
 `extent` 개체의 순위입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[extent::extent 생성자](../Topic/extent::extent%20Constructor.md)|`extent` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[extent::contains 메서드](../Topic/extent::contains%20Method.md)|지정된 `extent` 개체에 지정된 순위가 포함되는지 확인합니다.|  
|[extent::size 메서드](../Topic/extent::size%20Method.md)|범위\(요소의 단위에서\)의 총 선형 크기 단위를 반환합니다.|  
|[extent::tile 메서드](../Topic/extent::tile%20Method.md)|지정된 타일 크기를 사용하는 `tiled_extent` 개체를 생성합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[extent::operator\- 연산자](../Topic/extent::operator-%20Operator.md)|해당 `extent` 요소에서 `index` 요소를 빼고 만들어진 새 `extent` 개체를 반환합니다.|  
|[extent::operator\-\- 연산자](../Topic/extent::operator--%20Operator.md)|`extent` 개체의 각 요소를 감소시킵니다.|  
|[extent::operator\(mod\)\= 연산자](../Topic/extent::operator\(mod\)=%20Operator.md)|`extent` 개체의 각 요소를 숫자로 나눌 때의 나머지를 계산합니다.|  
|[extent::operator\*\= 연산자](../Topic/extent::operator*=%20Operator.md)|숫자로 `extent` 개체의 각 요소를 곱합니다.|  
|[extent::operator\/\= 연산자](../Topic/extent::operator-=%20Operator1.md)|숫자로 `extent` 개체의 각 요소를 나눕니다.|  
|[extent::operatorOperator](../Topic/extent::operatorOperator.md)|지정된 인덱스에 있는 요소를 반환합니다.|  
|[extent::operator\+ 연산자](../Topic/extent::operator+%20Operator.md)|해당 `index` 및 `extent` 요소 추가에 의해 만들어진 새 `extent` 개체를 반환합니다.|  
|[extent::operator\+\+ 연산자](../Topic/extent::operator++%20Operator.md)|`extent` 개체의 각 요소를 늘립니다.|  
|[extent::operator\+\= 연산자](../Topic/extent::operator+=%20Operator.md)|`extent` 개체의 각 요소에 지정한 수를 추가합니다.|  
|[extent::operator\= 연산자](../Topic/extent::operator=%20Operator.md)|다른 `extent` 개체의 내용을 여기로 복사합니다.|  
|[extent::operator\-\= 연산자](../Topic/extent::operator-=%20Operator2.md)|`extent` 개체의 각 요소에서 지정한 수를 뺍니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[extent::rank 상수](../Topic/extent::rank%20Constant.md)|`extent` 개체의 등급을 가져옵니다.|  
  
## 상속 계층  
 `extent`  
  
## 요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)