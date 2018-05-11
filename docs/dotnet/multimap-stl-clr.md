---
title: multimap (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- <cliext/map> header [STL/CLR]
- multimap class [STL/CLR]
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 168c6afec0f8f195d1315a54eff2794f7e3fd07e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="multimap-stlclr"></a>multimap(STL/CLR)
이 템플릿 클래스는 다양 한 길이의 요소 시퀀스를 양방향 액세스할 수 있는 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 여 `multimap` 하나의 요소 저장 하 고 각 노드의 정렬 된 나무를 균형 있게 (거의)으로 요소의 시퀀스를 관리할 수 있습니다. 요소 순서는 시퀀스와 경험해를 따라 이동 하는 매핑된 값에 대 한 키를 구성 됩니다.  
  
 아래 설명에 `GValue` 와 같습니다.  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `GKey` 동일 `Key` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Key^`  
  
 `GMapped` 동일 `Mapped` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Mapped^`  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
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
  
#### <a name="parameters"></a>매개 변수  
 Key  
 형식 제어 된 시퀀스의 요소의 핵심 구성 요소입니다.  
  
 매핑된  
 제어 된 시퀀스의 요소의 추가 구성 요소 형식입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[multimap::const_iterator(STL/CLR)](../dotnet/multimap-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[multimap::const_reference(STL/CLR)](../dotnet/multimap-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[multimap::const_reverse_iterator(STL/CLR)](../dotnet/multimap-const-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[multimap::difference_type(STL/CLR)](../dotnet/multimap-difference-type-stl-clr.md)|두 요소 사이의 거리 (서명 된 가능)의 형식입니다.|  
|[multimap::generic_container(STL/CLR)](../dotnet/multimap-generic-container-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|  
|[multimap::generic_iterator(STL/CLR)](../dotnet/multimap-generic-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|  
|[multimap::generic_reverse_iterator(STL/CLR)](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반대 반복기의 형식입니다.|  
|[multimap::generic_value(STL/CLR)](../dotnet/multimap-generic-value-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[multimap::iterator(STL/CLR)](../dotnet/multimap-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[multimap::key_compare(STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)|두 키에 대 한 순서 지정 하는 대리자입니다.|  
|[multimap::key_type(STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)|정렬 키의 형식입니다.|  
|[multimap::mapped_type(STL/CLR)](../dotnet/multimap-mapped-type-stl-clr.md)|각 키와 연결 된 매핑된 값의 형식입니다.|  
|[multimap::reference(STL/CLR)](../dotnet/multimap-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[multimap::reverse_iterator(STL/CLR)](../dotnet/multimap-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[multimap::size_type(STL/CLR)](../dotnet/multimap-size-type-stl-clr.md)|두 요소 사이의 (음수가) 거리의 형식입니다.|  
|[multimap::value_compare(STL/CLR)](../dotnet/multimap-value-compare-stl-clr.md)|두 요소 값에 대 한 순서 지정 하는 대리자입니다.|  
|[multimap::value_type(STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[multimap::begin(STL/CLR)](../dotnet/multimap-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[multimap::clear(STL/CLR)](../dotnet/multimap-clear-stl-clr.md)|모든 요소를 제거합니다.|  
|[multimap::count(STL/CLR)](../dotnet/multimap-count-stl-clr.md)|지정된 된 키와 일치 하는 요소 수를 계산 합니다.|  
|[multimap::empty(STL/CLR)](../dotnet/multimap-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[multimap::end(STL/CLR)](../dotnet/multimap-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[multimap::equal_range(STL/CLR)](../dotnet/multimap-equal-range-stl-clr.md)|지정된 키와 일치하는 범위를 찾습니다.|  
|[multimap::erase(STL/CLR)](../dotnet/multimap-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[multimap::find(STL/CLR)](../dotnet/multimap-find-stl-clr.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[multimap::insert(STL/CLR)](../dotnet/multimap-insert-stl-clr.md)|요소를 추가합니다.|  
|[multimap::key_comp(STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)|두 키에 대 한 순서 지정 대리자를 복사합니다.|  
|[multimap::lower_bound(STL/CLR)](../dotnet/multimap-lower-bound-stl-clr.md)|지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.|  
|[multimap::make_value(STL/CLR)](../dotnet/multimap-make-value-stl-clr.md)|값 개체를 만듭니다.|  
|[multimap::multimap(STL/CLR)](../dotnet/multimap-multimap-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[multimap::rbegin(STL/CLR)](../dotnet/multimap-rbegin-stl-clr.md)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[multimap::rend(STL/CLR)](../dotnet/multimap-rend-stl-clr.md)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[multimap::size(STL/CLR)](../dotnet/multimap-size-stl-clr.md)|요소 수를 계산합니다.|  
|[multimap::swap(STL/CLR)](../dotnet/multimap-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[multimap::to_array(STL/CLR)](../dotnet/multimap-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
|[multimap::upper_bound(STL/CLR)](../dotnet/multimap-upper-bound-stl-clr.md)|지정된 된 키와 일치 하는 범위의 끝을 찾습니다.|  
|[multimap::value_comp(STL/CLR)](../dotnet/multimap-value-comp-stl-clr.md)|두 요소 값에 대 한 순서 지정 대리자를 복사합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[multimap::operator=(STL/CLR)](../dotnet/multimap-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
|[operator!= (multimap)(STL/CLR)](../dotnet/operator-inequality-multimap-stl-clr.md)|있는지 여부를 확인 한 `multimap` 개체가 다른과 같지 않습니다. `multimap` 개체입니다.|  
|[operator< (multimap)(STL/CLR)](../dotnet/operator-less-than-multimap-stl-clr.md)|있는지 여부를 확인 한 `multimap` 개체를 사용 하면 다른 노드보다 작은지 `multimap` 개체입니다.|  
|[operator<= (multimap)(STL/CLR)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|있는지 여부를 확인 한 `multimap` 개체 보다 작거나 같으면 다른 `multimap` 개체입니다.|  
|[operator== (multimap)(STL/CLR)](../dotnet/operator-equality-multimap-stl-clr.md)|있는지 여부를 확인 한 `multimap` 개체는 다른 `multimap` 개체입니다.|  
|[operator> (multimap)(STL/CLR)](../dotnet/operator-greater-than-multimap-stl-clr.md)|있는지 여부를 확인 한 `multimap` 개체가 다른 노드보다 큰지 `multimap` 개체입니다.|  
|[operator>= (multimap)(STL/CLR)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)|있는지 여부를 확인 한 `multimap` 개체는 다른 보다 크거나 `multimap` 개체입니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스입니다.|  
|<xref:System.Collections.ICollection>|요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소의 그룹을 유지 합니다.|  
|ITree\<키, 값 >|제네릭 컨테이너를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 개별 노드로 제어 하는 시퀀스에 대 한 저장소를 해제 합니다. 다른 한 노드의 콘텐츠를 복사 하 여 되지 노드 간의 링크를 변경 하 여 순서가 지정 된 보관 하는 나무를 균형 있게 (거의)에 요소를 삽입 합니다. 즉, 삽입 하 고 나머지 요소를 방해 하지 않고 자유롭게 요소를 제거할 수 있습니다.  
  
 형식의 개체를 저장된 하는 대리자를 호출 하 여 제어 하는 시퀀스를 정렬 하는 개체 [multimap:: key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)합니다. Multimap; 생성할 때 저장된 대리자 개체를 지정할 수 있습니다. 기본값은 비교 없는 대리자 개체를 지정 하면 `operator<(key_type, key_type)`합니다. 멤버 함수를 호출 하 여이 저장 된 개체를 액세스할 [multimap:: key_comp (STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)`()`합니다.  
  
 이러한 대리자 개체 유형의 키에 대해 엄밀히 약한 정렬을 적용 해야 합니다 [multimap:: key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)합니다. 모든 두 개의 키 즉 `X` 및 `Y`:  
  
 `key_comp()(X, Y)` 동일한 부울 결과를 반환 모든 호출 합니다.  
  
 경우 `key_comp()(X, Y)` 가 true 이면 `key_comp()(Y, X)` false 이어야 합니다.  
  
 경우 `key_comp()(X, Y)` 가 true 이면 `X` 앞에 정렬를 라고 `Y`합니다.  
  
 경우 `!key_comp()(X, Y) && !key_comp()(Y, X)` 가 true 이면 `X` 및 `Y` 순서 지정이 동일할에 있다고 합니다.  
  
 모든 요소에 대해 `X` 앞에 `Y` 제어 된 시퀀스의 `key_comp()(Y, X)` 은 false입니다. (기본 대리자 개체에 대 한 키는 결코 감소 값입니다.) 템플릿 클래스와 달리 [map (STL/CLR)](../dotnet/map-stl-clr.md)를 템플릿 클래스의 개체 `multimap` 모든 요소에 대 한 키가 고유한 지 필요 하지 않습니다. (키가 두 개 이상 있을 수 있음 순서 지정이 동일할.)  
  
 각 요소에는 별도 키와 매핑된 값을 포함 합니다. 시퀀스는 시퀀스 (에 오면 로그 시간)에 조회, 삽입 및 수의 요소 수 로그에 비례 하는 작업의 임의 요소 제거를 허용 하는 방식으로 표시 됩니다. 또한, 요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 가리키고 있는 반복기만 무효화됩니다.  
  
 Multimap 의미 제어 된 시퀀스의 요소를 지정 하는 반복기를 제공 하는 인접 요소를 실행할 수 있는 양방향 반복기 지원 합니다. 반환 된 반복기에 해당 하는 특수 헤드 노드 [multimap:: end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`합니다. 있는 경우이 반복기는 제어 되는 시퀀스에서 마지막 요소를 연결할를 감소 시킬 수 있습니다. 헤드 노드에 도달 하는 multimap 반복기를 증가 시킬 수 있습니다 및 같음 비교 다음 `end()`합니다. 반환 된 반복기를 역 참조할 수 없습니다 하지만 `end()`합니다.  
  
 직접 숫자의 위치를 지정 하는 multimap 요소 참조할 수 없으며 참고-임의 액세스 반복기를 필요로 하 합니다.  
  
 Multimap 반복기 차례로 연결 된 컨테이너에 대 한 핸들을 저장 하는 해당 연결된 multimap 노드에 대 한 핸들을 저장 합니다. 반복기의 관련된 컨테이너 개체와만 사용할 수 있습니다. Multimap 반복기도 연결 된 해당 multimap 노드로 일부 multimap와 연결 된 유효한 상태를 유지 합니다. 유효한 반복기 dereferencable 연결은 액세스 또는 같지 않은 것으로 지정-요소 값을 변경 하려면 사용할 수 또한 `end()`합니다.  
  
 지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 컨테이너를 제거 합니다. 모든 요소를 지웁니다. 따라서 요소 형식이 ref 클래스는 컨테이너 보다 수명이 깁니다 컨테이너 요소가 있는지 확인 합니다. 단, 핸들의 컨테이너 하다 `not` 해당 요소를 제거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/매핑 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)