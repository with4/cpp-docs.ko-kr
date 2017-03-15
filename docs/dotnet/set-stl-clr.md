---
title: "set(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/set> 헤더[STL/CLR]"
  - "<set> 헤더[STL/CLR]"
  - "set 클래스[STL/CLR]"
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# set(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 양방향 액세스 할 수있는 요소의 가변 길이 시퀀스를 제어하는 개체에 대해 설명합니다.   `set`  컨테이너를 사용하여 각 저장 요소 시퀀스 요소의 균형 \(거의\) 정렬 된 트리 노드를 관리할 수 있습니다.  
  
 아래 설명에  `GValue` 는  `GKey`  와 같습니다,  문자에 참조형식이 있지 않는 이상  `Key`   `Key^`  와 동일시 됩니다.  
  
## 구문  
  
```  
template<typename Key>  
    ref class set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### 매개 변수  
 Key  
 제어되는 시퀀스에 있는 요소의 키 구성 요소 형식입니다.  
  
## 멤버  
  
|형식 정의|설명|  
|-----------|--------|  
|[set::const\_iterator](../dotnet/set-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[set::const\_reference](../dotnet/set-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[set::const\_reverse\_iterator](../dotnet/set-const-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 일정한 역방향 반복기의 유형입니다.|  
|[set::difference\_type](../dotnet/set-difference-type-stl-clr.md)|두 요소 사이의 \(부호가 있는\) 거리의 형식입니다.|  
|[set::generic\_container](../dotnet/set-generic-container-stl-clr.md)|컨테이너에 대한 제네릭 인터페이스의 형식입니다.|  
|[set::generic\_iterator](../dotnet/set-generic-iterator-stl-clr.md)|제네릭 인터페이스와 함께 사용하기 위한 컨테이너의 반복기의 형식입니다.|  
|[set::generic\_reverse\_iterator](../dotnet/set-generic-reverse-iterator-stl-clr.md)|컨테이너의 제네릭 인터페이스와 함께 사용하기 위한 역방향 반복기의 유형입니다.|  
|[set::generic\_value](../dotnet/set-generic-value-stl-clr.md)|제네릭 인터페이스와 함께 사용하기 위한 컨테이너의 요소의 형식입니다.|  
|[set::iterator](../dotnet/set-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[set::key\_compare](../dotnet/set-key-compare-stl-clr.md)|두 키의 순서 지정 대리자입니다..|  
|[set::key\_type](../dotnet/set-key-type-stl-clr.md)|정렬 키의 형식입니다.|  
|[set::reference](../dotnet/set-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[set::reverse\_iterator](../dotnet/set-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[set::size\_type](../dotnet/set-size-type-stl-clr.md)|두 요소 사이의 \(음수\) 거리의 형식입니다.|  
|[set::value\_compare](../dotnet/set-value-compare-stl-clr.md)|두 요소의 순서 지정 대리자입니다.|  
|[set::value\_type](../dotnet/set-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|-----------|--------|  
|[set::begin](../dotnet/set-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[set::clear](../dotnet/set-clear-stl-clr.md)|모든 요소를 제거합니다.|  
|[set::count](../dotnet/set-count-stl-clr.md)|지정된 된 키와 일치하는 요소를 계산합니다.|  
|[set::empty](../dotnet/set-empty-stl-clr.md)|테스트 요소가 있는지 여부를 표시합니다.|  
|[set::end](../dotnet/set-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[set::equal\_range](../dotnet/set-equal-range-stl-clr.md)|지정된 키와 일치하는 범위를 찾습니다.|  
|[set::erase](../dotnet/set-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[set::find](../dotnet/set-find-stl-clr.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[set::insert](../dotnet/set-insert-stl-clr.md)|요소를 추가합니다.|  
|[set::key\_comp](../dotnet/set-key-comp-stl-clr.md)|두 키의 순서 지정 대리자를 복사합니다.|  
|[set::lower\_bound](../dotnet/set-lower-bound-stl-clr.md)|지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.|  
|[set::make\_value](../dotnet/set-make-value-stl-clr.md)|값 개체를 생성합니다.|  
|[set::rbegin](../dotnet/set-rbegin-stl-clr.md)|역방향 제어되는 시퀀스의 시작을 지정합니다.|  
|[set::rend](../dotnet/set-rend-stl-clr.md)|역방향 제어되는 시퀀스의 끝을 지정합니다.|  
|[set::set](../dotnet/set-set-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[set::size](../dotnet/set-size-stl-clr.md)|요소의 수를 셉니다.|  
|[set::swap](../dotnet/set-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[set::to\_array](../dotnet/set-to-array-stl-clr.md)|제어 되는 시퀀스를 새 배열에 복사합니다.|  
|[set::upper\_bound](../dotnet/set-upper-bound-stl-clr.md)|지정된 키와 일치하는 범위의 끝을 찾습니다.|  
|[set::value\_comp](../dotnet/set-value-comp-stl-clr.md)|두 요소 값의 순서 지정 대리자를 복사합니다.|  
  
|연산자|설명|  
|---------|--------|  
|[set::operator\=](../dotnet/set-operator-assign-stl-clr.md)|제어된 시퀀스를 대체합니다.|  
|[operator\!\= \(set\)](../dotnet/operator-inequality-set-stl-clr.md)|`set`  개체가 다른  `set`  개체와 같지 않은지 확인하십시오.|  
|[operator\< \(set\)](../dotnet/operator-less-than-set-stl-clr.md)|`set`  개체가 다른  `set`  개체보다 작은지 확인하십시오.|  
|[operator\<\= \(set\)](../dotnet/operator-less-or-equal-set-stl-clr.md)|`set` 개체가 다른 `set`개체보다 작거나 같은지 확인하십시오.|  
|[operator\=\= \(set\)](../dotnet/operator-equality-set-stl-clr.md)|`set`  개체가 다른  `set`  개체와 같은지 확인하십시오.|  
|[operator\> \(set\)](../dotnet/operator-greater-than-set-stl-clr.md)|`set`  개체가 다른  `set`  개체보다 큰지 확인하십시오.|  
|[operator\>\= \(set\)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|`set` 개체가 다른 `set`개체보다 크거나 같은지 확인하십시오.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|개체 복제|  
|<xref:System.Collections.IEnumerable>|요소를 시퀀스입니다.|  
|<xref:System.Collections.ICollection>|요소 그룹을 유지 관리합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|형식의 요소 시퀀스입니다.|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소 그룹을 유지 관리합니다.|  
|ITree\<키, 값\>|일반 컨테이너를 유지 합니다.|  
  
## 설명  
 개체를 할당하고 개별 노드를 제어하는 순서에 대한 저장소를 해제합니다.  그것은 다른 하나의 노드의 내용을 복사함으로써, 노드 간의 링크를 ​​변경하여 정렬 유지하고 평형 트리에 요소를 삽입합니다.  즉, 삽입 하 고 나머지 요소를 방해 하ㅁ즉, 나머지 요소를 방해하지 않고 자유롭게 요소를 삽입하고 제거 할 수 있음을 의미합니다.지 않고 자유롭게 요소를 제거할 수 있습니다.  
  
 개체는 [set::key\_compare](../dotnet/set-key-compare-stl-clr.md) 형식의 저장된 대리자 개체를 호출하여 컨트롤하는 시퀀스를 정렬합니다.  집합을 구성할 때 저장된 대리자 개체를 지정할 수 있습니다. 개체를 지정하지 않으면 기본값은 비교 `operator<(key_type, key_type)`입니다  [set::key\_comp](../dotnet/set-key-comp-stl-clr.md)  `()`  멤버 함수를 호출하여 저장된 개체에 액세스합니다.  
  
 대리자 개체는 [set::key\_type](../dotnet/set-key-type-stl-clr.md) 형식의 키에 엄격한 순서를 적용해야 합니다 .  두 개의 키  `X`  및  `Y` 을 의미합니다.  
  
 `key_comp()(X, Y)`은 호출할 때마다 동일한 부울을 반환합니다.  
  
 `key_comp()(X, Y)`  가 true 이면  `key_comp()(Y, X)` 는 false 여야 합니다.  
  
 `key_comp()(X, Y)`  가 true 이면  `X` 는  `Y`  이전에 정렬되어 있어야 한다고 합니다.  
  
 `!key_comp()(X, Y) && !key_comp()(Y, X)`  가 true 이면  `X`  및  `Y` 는 순서가 있어야 한다고 합니다.  
  
 제어 되는 시퀀스에서  `Y`  앞에 있는 모든  `X`  요소에 대해서   `key_comp()(Y, X)`  는 false입니다. \(기본 대리자 객체의 경우, 키 값이 감소하지 않습니다.\) [set](../dotnet/set-stl-clr.md) 템플릿 클래스와는 달리 ,  `set`  템플릿 클래스의 개체는 모든 요소에 대한 키가 고유하지 않아도 됩니다. \(두 개 이상의 키가 동일한 순서입니다.\)  
  
 각 요소는 의미와 값 모두로 사용됩니다.  시퀀스는 조회, 삽입 및 배열 내의 요소 수 \(로그 시간\)의 대수에 비례 한 작업 수를 갖는 모든 요소의 제거를 허용하도록 표시되어있다.  또한, 요소를 삽입하는 것은 더 반복자를 무효화하지 않고, 요소를 제거하면 제거 된 요소를 가리 만 반복자를 무효화합니다.  
  
 세트는 제어 된 시퀀스의 요소를 지정하는 반복기 주어진 인접 요소를 단계별로 실행할 수 있습니다 즉, 양방향 반복자를 지원합니다.  특수한 헤드 노드는 [set::end](../dotnet/set-end-stl-clr.md)  `()` 을 반환하는 반복기에 해당합니다.  존재하는 경우, 제어 된 시퀀스의 마지막 요소에 도달하는 반복자를 감소시킬 수 있습니다.  헤드 노드에 도달하는 집합 반복기를 증가 시킬 수있고, 그런다음  `end()` 와 같은지 비교합니다.  하지만  `end()` 을 반환하는 반복기를 역참조할 수 없습니다.  
  
 임의 액세스 반복기를 필요로 합니다 \- 직접 그 숫자 위치 지정된 세트의 요소를 참조 할 수 없다는 점에 유의하십시오.  
  
 집합의 반복자는 다시 관련 컨테이너에 대한 핸들을 저장하는 관련 집합 노드에 대한 핸들을 저장합니다.  컨테이너 개체와 연결된 반복기만 사용할 수 있습니다.  집합의 반복자는 오랫동안 그와 관련된 일련의 노드가 일부 집합와 연관​​되는 한 유효합니다.  또한 유효한 반복기는 dereferencable입니다\-그것이 지칭 요소 값을 액세스하거나 변경하는 데 사용할 수 있습니다\-  `end()` 와 동일하지 않습니다.  
  
 삭제 또는 요소를 제거하는 것은 그 저장된 값의 소멸자를 호출합니다.  컨테이너를 파괴하는 모든 요소를 ​​삭제합니다.  따라서 요소 형식이 ref 클래스 컨테이너는 요소가 컨테이너 밖에 있는지 확인합니다.  그런, 핸들의 컨테이너는  `not`  해당 요소를 제거합니다.  
  
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)