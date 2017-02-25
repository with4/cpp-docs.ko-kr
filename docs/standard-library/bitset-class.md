---
title: "bitset 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bitset/std::bitset"
  - "std::bitset"
  - "std.bitset"
  - "bitset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitset 클래스"
ms.assetid: 28b86964-87b4-429c-8124-b6c251b6c50b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# bitset 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일련의 항목 또는 조건에 대한 플래그를 유지하는 간단한 방법을 제공하는 고정 비트 수로 구성된 시퀀스를 저장하는 개체의 유형에 대해 설명합니다.  bitset 클래스에서는 비트 컬렉션을 포함하고 각 비트에 대한 constant\-time 액세스 권한을 제공하는 형식 bitset의 개체에 대한 작업을 지원합니다.  
  
## 구문  
  
```  
  
     template <size_t   
     N  
     >  
class bitset  
```  
  
#### 매개 변수  
 *N*  
 컴파일 시 알아야 하는 형식 **size\_t**의 0이 아닌 정수를 사용하여 bitset 개체의 비트 수를 지정합니다.  
  
## 설명  
 유사한 [vector\<bool\> 클래스](../standard-library/vector-bool-class.md)와 달리 bitset 클래스는 반복기가 없으며 표준 템플릿 라이브러리 컨테이너가 아닙니다.  또한 **bitset\<N\>**가 선언되었을 때 템플릿 매개 변수 **N**으로 지정된 크기에 따라 컴파일 시 고정되어 있는 일부 특정 크기가 됨으로써 vector\<bool\>과도 다릅니다.  
  
 비트는 값이 1이면 설정되고, 값이 0이면 재설정 합니다.  한 비트를 뒤집거나 토글한다는 것은 값을 1에서 0 또는 0에서 1로 변경하는 것입니다.  bitset의 **N** 비트는 0에서 **N**\-1 범위의 정수 값으로 인덱싱되며, 여기서 0은 첫 번째 비트 위치를 인덱싱하고 **N**\-1은 최종 비트 위치를 인덱싱합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[비트 세트](../Topic/bitset::bitset.md)|클래스 `bitset<N>`의 개체를 생성하고 비트를 0, 지정된 일부 값 또는 문자열의 문자에서 얻은 값으로 초기화합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/bitset::element_type.md)|데이터 형식 `bool`의 동의어이고 `bitset`에서 요소 비트를 참조하는 데 사용할 수 있는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[all](../Topic/bitset::all.md)|이 `bitset`에 있는 모든 비트를 테스트하여 모두 `true`로 설정되었는지 여부를 확인합니다.|  
|[모두](../Topic/bitset::any.md)|멤버 함수는 시퀀스의 모든 비트가 1로 설정되었는지 여부를 테스트합니다.|  
|[count](../Topic/bitset::count.md)|멤버 함수는 비트 시퀀스에 설정된 비트 수를 반환합니다.|  
|[flip](../Topic/bitset::flip.md)|`bitset`에 있는 모든 비트의 값을 토글하거나 지정된 위치에서 단일 비트를 토글합니다.|  
|[없음](../Topic/bitset::none.md)|`bitset` 개체에서 1로 설정된 비트가 없는지 테스트합니다.|  
|[다시 설정](../Topic/bitset::reset.md)|`bitset`에 있는 모든 비트를 0으로 재설정하거나 지정된 위치의 비트를 0으로 재설정합니다.|  
|[set](../Topic/bitset::set.md)|`bitset`에 있는 모든 비트를 1로 설정하거나 지정된 위치의 비트를 1로 설정합니다.|  
|[size](../Topic/bitset::size.md)|`bitset` 개체의 비트 수를 반환합니다.|  
|[테스트](../Topic/bitset::test.md)|`bitset`에서 지정된 위치의 비트가 1로 설정되어 있는지 테스트합니다.|  
|[to\_string](../Topic/bitset::to_string.md)|`bitset` 개체를 문자열 표현으로 변환합니다.|  
|[to\_ullong](../Topic/bitset::to_ullong.md)|`bitset`에 있는 비트 값의 합을 `unsigned long long`로 반환합니다.|  
|[to\_ulong](../Topic/bitset::to_ulong.md)|`bitset` 개체를 `bitset`을 초기화하는 데 사용되는 경우 포함된 비트 시퀀스를 생성할 `unsigned long`로 변환합니다.|  
  
### 멤버 클래스  
  
|||  
|-|-|  
|[참조](../Topic/bitset::reference.md)|`bitset`의 `operator[]`에 대한 도우미 클래스로서 개별 비트에 액세스하고 조작하는 데 사용되는 `bitset`에 포함된 비트를 참조하는 프록시 클래스입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\!\=](../Topic/bitset::operator!=.md)|지정한 `bitset`와 다른지 알기 위해 대상 `bitset`을 테스트합니다.|  
|[operator&\=](../Topic/bitset::operator&=.md)|논리적 `AND` 작업과 bitsets의 비트 조합을 수행합니다.|  
|[연산자 \<\<](../Topic/bitset::operator%3C%3C.md)|왼쪽의 `bitset`에 있는 비트를 지정된 위치 수만큼 이동하고 결과를 새 `bitset`에 반환합니다.|  
|[operator\<\<\=](../Topic/bitset::operator%3C%3C=.md)|왼쪽의 `bitset`에 있는 비트를 지정된 위치 수만큼 이동하고 결과를 대상으로 지정된 `bitset`에 반환합니다.|  
|[연산자\=\=](../Topic/bitset::operator==.md)|지정한 `bitset`와 같은지 알기 위해 대상 `bitset`을 테스트합니다.|  
|[연산자 \>\>](../Topic/bitset::operator%3E%3E.md)|오른쪽의 `bitset`에 있는 비트를 지정된 위치 수만큼 이동하고 결과를 새 `bitset`에 반환합니다.|  
|[operator\>\>\=](../Topic/bitset::operator%3E%3E=.md)|오른쪽의 `bitset`에 있는 비트를 지정된 위치 수만큼 이동하고 결과를 대상으로 지정된 `bitset`에 반환합니다.|  
|[operator&#91;&#93;](../Topic/bitset::operator.md)|`bitset`을 수정할 수 있을 경우 `bitset`에서 지정된 위치의 비트에 대한 참조를 반환하고, 그렇지 않으면 해당 위치서 비트 값을 반환합니다.|  
|[operator^\=](../Topic/bitset::operator%5E=.md)|배타적 `OR` 작업과 bitsets의 비트 조합을 수행합니다.|  
|[operator&#124;\=](../Topic/bitset::operator%7C=.md)|포괄적 `OR` 작업과 bitsets의 비트 조합을 수행합니다.|  
|[operator~](../Topic/bitset::operator~.md)|대상 `bitset`의 모든 비트를 토글하고 결과를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<bitset\>  
  
 **네임스페이스:** std