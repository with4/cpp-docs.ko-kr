---
title: hash_set (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set
dev_langs:
- C++
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_set class [STL/CLR]
- <hash_set> header [STL/CLR]
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63b43a116848ff67deb9c62c04849aa5afc6dbc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="hashset-stlclr"></a>hash_set(STL/CLR)
이 템플릿 클래스는 다양 한 길이의 요소 시퀀스를 양방향 액세스할 수 있는 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 여 `hash_set` 가 양방향을 저장 하는 각 테이블 항목 연결 된 목록 노드 및 한 개의 요소 저장 노드마다의 해시 테이블로 요소의 시퀀스를 관리 합니다. 각 요소의 값은 시퀀스를 정렬 하기 위한 키로 사용 됩니다.  
  
 아래 설명에 `GValue` 동일 `GKey`는 다시 됩니다 동일 `Key` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Key^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Key>  
    ref class hash_set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>매개 변수  
 Key  
 형식 제어 된 시퀀스의 요소의 핵심 구성 요소입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[hash_set::const_iterator(STL/CLR)](../dotnet/hash-set-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[hash_set::const_reference(STL/CLR)](../dotnet/hash-set-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[hash_set::const_reverse_iterator(STL/CLR)](../dotnet/hash-set-const-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[hash_set::difference_type(STL/CLR)](../dotnet/hash-set-difference-type-stl-clr.md)|두 요소 사이의 거리 (서명 된 가능)의 형식입니다.|  
|[hash_set::generic_container(STL/CLR)](../dotnet/hash-set-generic-container-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|  
|[hash_set::generic_iterator(STL/CLR)](../dotnet/hash-set-generic-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|  
|[hash_set::generic_reverse_iterator(STL/CLR)](../dotnet/hash-set-generic-reverse-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반대 반복기의 형식입니다.|  
|[hash_set::generic_value(STL/CLR)](../dotnet/hash-set-generic-value-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[hash_set::hasher(STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)|키에 대 한 해시 하는 대리자입니다.|  
|[hash_set::iterator(STL/CLR)](../dotnet/hash-set-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[hash_set::key_compare(STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)|두 키에 대 한 순서 지정 하는 대리자입니다.|  
|[hash_set::key_type(STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)|정렬 키의 형식입니다.|  
|[hash_set::reference(STL/CLR)](../dotnet/hash-set-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[hash_set::reverse_iterator(STL/CLR)](../dotnet/hash-set-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[hash_set::size_type(STL/CLR)](../dotnet/hash-set-size-type-stl-clr.md)|두 요소 사이의 (음수가) 거리의 형식입니다.|  
|[hash_set::value_compare(STL/CLR)](../dotnet/hash-set-value-compare-stl-clr.md)|두 요소 값에 대 한 순서 지정 하는 대리자입니다.|  
|[hash_set::value_type(STL/CLR)](../dotnet/hash-set-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[hash_set::begin(STL/CLR)](../dotnet/hash-set-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[hash_set::bucket_count(STL/CLR)](../dotnet/hash-set-bucket-count-stl-clr.md)|버킷 수를 계산합니다.|  
|[hash_set::clear(STL/CLR)](../dotnet/hash-set-clear-stl-clr.md)|모든 요소를 제거합니다.|  
|[hash_set::count(STL/CLR)](../dotnet/hash-set-count-stl-clr.md)|지정된 된 키와 일치 하는 요소 수를 계산 합니다.|  
|[hash_set::empty(STL/CLR)](../dotnet/hash-set-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[hash_set::end(STL/CLR)](../dotnet/hash-set-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[hash_set::equal_range(STL/CLR)](../dotnet/hash-set-equal-range-stl-clr.md)|지정된 키와 일치하는 범위를 찾습니다.|  
|[hash_set::erase(STL/CLR)](../dotnet/hash-set-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[hash_set::find(STL/CLR)](../dotnet/hash-set-find-stl-clr.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[hash_set::hash_delegate(STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md)|키에 대 한 해시 대리자를 복사합니다.|  
|[hash_set::hash_set(STL/CLR)](../dotnet/hash-set-hash-set-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[hash_set::insert(STL/CLR)](../dotnet/hash-set-insert-stl-clr.md)|요소를 추가합니다.|  
|[hash_set::key_comp(STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)|두 키에 대 한 순서 지정 대리자를 복사합니다.|  
|[hash_set::load_factor(STL/CLR)](../dotnet/hash-set-load-factor-stl-clr.md)|버킷당 평균 요소 수를 계산합니다.|  
|[hash_set::lower_bound(STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)|지정된 된 키와 일치 하는 범위의 시작 부분을 찾습니다.|  
|[hash_set::make_value(STL/CLR)](../dotnet/hash-set-make-value-stl-clr.md)|값 개체를 만듭니다.|  
|[hash_set::max_load_factor(STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md)|버킷당 최대 요소 수를 가져오거나 설정합니다.|  
|[hash_set::rbegin(STL/CLR)](../dotnet/hash-set-rbegin-stl-clr.md)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[hash_set::rehash(STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)|해시 테이블을 다시 빌드합니다.|  
|[hash_set::rend(STL/CLR)](../dotnet/hash-set-rend-stl-clr.md)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[hash_set::size(STL/CLR)](../dotnet/hash-set-size-stl-clr.md)|요소 수를 계산합니다.|  
|[hash_set::swap(STL/CLR)](../dotnet/hash-set-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[hash_set::to_array(STL/CLR)](../dotnet/hash-set-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
|[hash_set::upper_bound(STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)|지정된 된 키와 일치 하는 범위의 끝을 찾습니다.|  
|[hash_set::value_comp(STL/CLR)](../dotnet/hash-set-value-comp-stl-clr.md)|두 요소 값에 대 한 순서 지정 대리자를 복사합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[hash_set::operator=(STL/CLR)](../dotnet/hash-set-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스입니다.|  
|<xref:System.Collections.ICollection>|요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소의 그룹을 유지 합니다.|  
|IHash\<키, 값 >|제네릭 컨테이너를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 양방향 연결된 리스트에 개별 노드로 제어 하는 시퀀스에 대 한 저장소를 해제 합니다. 액세스 속도 개체도 또는 유지 관리를 일련의 하위 목록, 목록 전체를 효과적으로 관리 (해시 테이블) 목록에 대 한 포인터의 다양 한 길이의 배열 버킷을 합니다. 다른 한 노드의 콘텐츠를 복사 하 여 되지 노드 간의 링크를 변경 하 여 순서가 지정 된 보관 하는 버킷에 요소를 삽입 합니다. 즉, 삽입 하 고 나머지 요소를 방해 하지 않고 자유롭게 요소를 제거할 수 있습니다.  
  
 개체 형식의 저장된 대리자 개체를 호출 하 여 제어 하는 각 버킷 정렬 [hash_set:: key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)합니다. Hash_set; 생성할 때 저장된 대리자 개체를 지정할 수 있습니다. 기본값은 비교 없는 대리자 개체를 지정 하면 `operator<=(key_type, key_type)`합니다.  
  
 멤버 함수를 호출 하 여 저장된 대리자 개체를 액세스할 [hash_set:: key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`합니다. 형식의 키 간의 순서 지정이 동일할 대리자 개체를 정의 해야 [hash_set:: key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)합니다. 모든 두 개의 키 즉 `X` 및 `Y`:  
  
 `key_comp()(X, Y)` 동일한 부울 결과를 반환 모든 호출 합니다.  
  
 경우 `key_comp()(X, Y) && key_comp()(Y, X)` 가 true 이면 `X` 및 `Y` 순서 지정이 동일할에 있다고 합니다.  
  
 처럼 동작 하는 모든 정렬 규칙 `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` 또는 `operator==(key_type, key_type)` eqivalent 순서을 정의 합니다.  
  
 컨테이너도 유지만 요소가 해당 레지스트리 키 순서 지정이 동일할 (있고 동일한 정수 값에는 해시) 버킷 내 인접 note 합니다. 템플릿 클래스와 달리 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)를 템플릿 클래스의 개체 `hash_set` 모든 요소에 대 한 키가 고유한 지 확인 합니다. (두 개의 키가 동일 하 게 정렬.)  
  
 개체 형식의 저장된 대리자 개체를 호출 하 여 지정된 된 정렬 키를 포함 해야 버킷을 결정 [hash_set:: hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)합니다. 멤버 함수를 호출 하 여이 저장 된 개체를 액세스할 [hash_set:: hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` 키 값에 따라 달라 지는 정수 값을 가져올 수 있습니다. Hash_set; 생성할 때 저장된 대리자 개체를 지정할 수 있습니다. 기본값은 함수 없는 대리자 개체를 지정 하면 `System::Object::hash_value(key_type)`합니다. 즉, 모든 키에 대 한 `X` 및 `Y`:  
  
 `hash_delegate()(X)` 각 호출에서 동일한 정수 결과 반환합니다.  
  
 경우 `X` 및 `Y` 순서 지정이 동일할, 다음 `hash_delegate()(X)` 와 동일한 정수 결과 반환 해야 `hash_delegate()(Y)`합니다.  
  
 각 요소는 키와 값으로 사용 됩니다. 시퀀스는 조회, 삽입 및 모범 사례에 적어도 (일정 시간)-시퀀스의 요소 수에 관계 없이 동일한 작업 수가 임의 요소 제거를 허용 하는 방식으로 표시 됩니다. 또한, 요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 가리키고 있는 반복기만 무효화됩니다.  
  
 해시 된 값 균일 하 게 배포 되지 않은 경우 이때 해시 테이블 수 중복 제거 합니다. 극단-항상는 동일한 값을 반환 하는 해시 함수에 대 한 조회, 삽입 및 제거 됩니다 (선형 시간) 시퀀스의 요소 수에 비례 합니다. 컨테이너 적절 한 해시 함수, 평균 버킷 크기 선택 위해 노력 하 고 있지만 해시 테이블 크기 (총 수, 버킷), 이러한 선택 항목 중 일부 또는 모두 재정의할 수 있습니다. 예를 들어, 함수, 참조 [hash_set:: max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) 및 [hash_set:: rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)합니다.  
  
 hash_set 제어 된 시퀀스의 요소를 지정 하는 반복기를 제공 하는 인접 요소를 실행할 수를 의미 있는 양방향 반복기를 지원 합니다. 반환 된 반복기에 해당 하는 특수 헤드 노드 [hash_set:: end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`합니다. 있는 경우이 반복기는 제어 되는 시퀀스에서 마지막 요소를 연결할를 감소 시킬 수 있습니다. 헤드 노드에 도달 하는 hash_set 반복기를 증가 시킬 수 있습니다 및 같음 비교 다음 `end()`합니다. 반환 된 반복기를 역 참조할 수 없습니다 하지만 `end()`합니다.  
  
 참조할 수 없습니다. 직접 나와 임의 액세스 반복기를 필요로 하는 숫자 위치-hash_set 요소는 참고 사항  
  
 Hash_set 반복기에 대 한 핸들에 연결 된 컨테이너에 대 한 핸들을 저장 하는 해당 관련된 hash_set 노드를 저장 합니다. 반복기의 관련된 컨테이너 개체와만 사용할 수 있습니다. Hash_set 반복기도 관련된 hash_set 노드 일부 hash_set와 연결 된 유효한 상태를 유지 합니다. 유효한 반복기 dereferencable 연결은 액세스 또는 같지 않은 것으로 지정-요소 값을 변경 하려면 사용할 수 또한 `end()`합니다.  
  
 지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 컨테이너를 제거 합니다. 모든 요소를 지웁니다. 따라서 요소 형식이 ref 클래스는 컨테이너 보다 수명이 깁니다 컨테이너 요소가 있는지 확인 합니다. 단, 핸들의 컨테이너 하다 `not` 해당 요소를 제거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_set](../dotnet/hash-set-stl-clr.md)   
 [hash_set](../dotnet/hash-set-stl-clr.md)   
 [map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)