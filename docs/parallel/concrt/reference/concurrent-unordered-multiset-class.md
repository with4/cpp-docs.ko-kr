---
title: "concurrent_unordered_multiset 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_set/concurrency::concurrent_unordered_multiset
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_multiset class
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 19244e5527207f852256e646abd18ad298fb28cd
ms.openlocfilehash: 7a4b5edab0fdf1fcc18e223c859ca2859173154f
ms.lasthandoff: 02/24/2017

---
# <a name="concurrentunorderedmultiset-class"></a>concurrent_unordered_multiset 클래스
`concurrent_unordered_multiset` 클래스는 다양 한 길이의 K. 형식의 요소 시퀀스를 제어 하는 동시성이 컨테이너 시퀀스 동시성이 수 있도록 하는 방식으로 표현 됩니다 추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_multiset : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
 _Hasher,
    key_equality>,
 _Allocator_type,
    true>>;
```   
  
#### <a name="parameters"></a>매개 변수  
 `K`  
 키 형식입니다.  
  
 `_Hasher`  
 해시 함수 개체 형식입니다. 이 인수는 선택 사항이며 기본값은 `std::hash<``K``>`입니다.  
  
 `key_equality`  
 같음 비교 함수 개체 형식입니다. 이 인수는 선택 사항이며 기본값은 `std::equal_to<``K``>`입니다.  
  
 `_Allocator_type`  
 할당 및 동시 벡터에 대 한 메모리 할당 취소 하는 방법에 대 한 세부 정보를 캡슐화 하는 저장 된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `std::allocator<``K``>`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`allocator_type`|저장소 관리를 위한 할당자의 형식입니다.|  
|`const_iterator`|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|`const_local_iterator`|제어되는 시퀀스에 대한 상수 버킷 반복기의 형식입니다.|  
|`const_pointer`|요소에 대한 상수 포인터의 형식입니다.|  
|`const_reference`|요소에 대한 상수 참조의 형식입니다.|  
|`difference_type`|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|`hasher`|해시 함수의 형식입니다.|  
|`iterator`|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|`key_equal`|비교 함수의 형식입니다.|  
|`key_type`|정렬 키의 형식입니다.|  
|`local_iterator`|제어되는 시퀀스에 대한 버킷 반복기의 형식입니다.|  
|`pointer`|요소에 대한 포인터의 형식입니다.|  
|`reference`|요소에 대한 참조의 형식입니다.|  
|`size_type`|두 요소 사이의 부호가 없는 거리의 형식입니다.|  
|`value_type`|요소의 형식입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[concurrent_unordered_multiset 생성자](#ctor)|오버로드됨. 순서가 지정 되지 않은 동시 multiset을 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[hash_function 메서드](#hash_function)|저장 된 해시 함수 개체를 반환합니다.|  
|[insert 메서드](#insert)|오버로드됨. 요소를 추가 하는 `concurrent_unordered_multiset` 개체입니다.|  
|[key_eq 메서드](#key_eq)|저장 된 같음 비교 함수 개체입니다.|  
|[swap 메서드](#swap)|두 개의의 내용을 바꿉니다 `concurrent_unordered_multiset` 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.|  
|[unsafe_erase 메서드](#unsafe_erase)|오버로드됨. 요소를 제거는 `concurrent_unordered_multiset` 지정 된 위치에 있습니다. 이 메서드는 동시성이 보장 되지 않습니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator = 연산자](#operator_eq)|오버로드됨. 다른 할당 `concurrent_unordered_multiset` 여기에 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.|  
  
## <a name="remarks"></a>주의  
 에 대 한 자세한 내용은 `concurrent_unordered_multiset` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concurrent_unordered_set.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>시작 

 동시 컨테이너의 첫 번째 요소를 가리키는 반복기를 반환 합니다. 이 방법은 동시성 안전 합니다.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 첫 번째 요소를 사용 하는 반복기입니다.  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 동시 컨테이너의 첫 번째 요소를 가리키는 상수 반복기를 반환 합니다. 이 방법은 동시성 안전 합니다.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 첫 번째 요소에는 const 반복기입니다.  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 동시 컨테이너의 마지막 요소 다음에 나오는 위치를 가리키는 상수 반복기를 반환 합니다. 이 방법은 동시성 안전 합니다.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 마지막 요소 다음의 위치는 const 반복기입니다.  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>지우기 

 동시 컨테이너의 모든 요소를 지웁니다. 이 함수는 동시성 안전 하지 않습니다.  
  
```
void clear();
```  
  
##  <a name="a-namectora-concurrentunorderedmultiset"></a><a name="ctor"></a>concurrent_unordered_multiset 

 순서가 지정 되지 않은 동시 multiset을 생성합니다.  
  
```
explicit concurrent_unordered_multiset(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_multiset(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_multiset(
    concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Iterator`  
 입력 반복기의 형식입니다.  
  
 `_Number_of_buckets`  
 순서가 지정되지 않은 이 multiset에 대한 초기 버킷 수입니다.  
  
 `_Hasher`  
 정렬되지 않은 multiset에 대한 해시 함수입니다.  
  
 `key_equality`  
 정렬되지 않은 이 multiset에 대한 같음 비교 함수입니다.  
  
 `_Allocator`  
 정렬되지 않은 이 multiset의 할당자입니다.  
  
 `first`  
 `last`  
 `_Uset`  
 소스 `concurrent_unordered_multiset` 개체는 요소를 이동시킵니다.  
  
### <a name="remarks"></a>주의  
 모든 생성자는 할당자 개체 `_Allocator`를 저장하고 정렬되지 않은 multiset을 초기화합니다.  
  
 첫 번째 생성자는 비어 있는 초기 multiset을 지정하고 사용할 버킷 수, 해시 함수, 같음 함수 및 할당자 형식을 명시적으로 지정합니다.  
  
 두 번째 생성자는 정렬되지 않은 multiset의 할당자를 지정합니다.  
  
 세 번째 생성자는 반복기 범위에서 제공 하는 값을 지정 [ `_Begin`, `_End`).  
  
 네 번째와 다섯 번째 생성자는 정렬되지 않은 동시 multiset `_Uset`의 복사본을 지정합니다.  
  
 마지막 생성자는 정렬되지 않은 동시 multiset `_Uset`의 이동을 지정합니다.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>개수 

 지정된 된 키와 일치 하는 요소의 수를 계산 합니다. 이 함수는 동시성 안전 합니다.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 검색할 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키 컨테이너에 나타나는 횟수 시간.  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>빈 

 요소가 있는지 여부를 테스트합니다. 이 방법은 동시성 안전 합니다.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 `true`동시 컨테이너 비어 있는 경우 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 동시 삽입이 있을 경우 동시 컨테이너 비어 여부 반환 값을 읽기도 전에이 함수를 호출한 직후, 변경 될 수 있습니다.  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>끝 

 동시 컨테이너의 마지막 요소 다음에 나오는 위치를 가리키는 반복기를 반환 합니다. 이 방법은 동시성 안전 합니다.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 마지막 요소 다음에 나오는 위치를 사용 하는 반복기입니다.  
  
##  <a name="a-nameequalrangea-equalrange"></a><a name="equal_range"></a>equal_range 

 지정된 된 키와 일치 하는 범위를 찾습니다. 이 함수는 동시성 안전 합니다.  
  
```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 키 값에 대 한 검색입니다.  
  
### <a name="return-value"></a>반환 값  
 A [쌍](http://msdn.microsoft.com/en-us/32e72d66-3020-4cb9-92c3-f7a5fa7998ff) 여기서 첫 번째 요소는 시작 부분에 대 한 반복기 하 고 두 번째 요소는 반복기가 범위 끝에 있습니다.  
  
### <a name="remarks"></a>주의  
 동시 삽입이 발생할 시작 반복기와 마지막 바로 다음 반복기는 삽입 될 추가 키에 대 한 것 같습니다.  
  
##  <a name="a-namefinda-find"></a><a name="find"></a>찾기 

 지정된 키와 일치하는 요소를 찾습니다. 이 함수는 동시성 안전 합니다.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 키 값에 대 한 검색입니다.  
  
### <a name="return-value"></a>반환 값  
 위치를 가리키는 반복기는 제공 된 키를 일치 하는 첫 번째 요소 또는 반복기 `end()` 이러한 요소가 없는 경우.  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 이 동시 컨테이너에 대 한 저장 된 할당자 개체를 반환합니다. 이 방법은 동시성 안전 합니다.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 동시 컨테이너에 대 한 저장 된 할당자 개체입니다.  
  
##  <a name="a-namehashfunctiona-hashfunction"></a><a name="hash_function"></a>hash_function 

 저장 된 해시 함수 개체를 반환합니다.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>반환 값  
 저장된 해시 함수 개체입니다.  
  
##  <a name="a-nameinserta-insert"></a><a name="insert"></a>삽입 

 요소를 추가 하는 `concurrent_unordered_multiset` 개체입니다.  
  
```
iterator insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
iterator insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Iterator`  
 삽입에 사용되는 반복기 형식입니다.  
  
 `V`  
 삽입한 값의 형식입니다.  
  
 `value`  
 삽입할 값입니다.  
  
 `_Where`  
 삽입 지점을 검색할 시작 위치입니다.  
  
 `first`  
 삽입할 범위의 시작 부분입니다.  
  
 `last`  
 삽입할 범위의 끝입니다.  
  
### <a name="return-value"></a>반환 값  
 삽입 위치를 가리키는 반복기입니다.  
  
### <a name="remarks"></a>주의  
 첫 번째 멤버 함수는 제어되는 시퀀스에 요소 `value`를 삽입한 다음 해당 요소를 지정하는 반복기를 반환합니다.  
  
 삽입을 반환 하는 두 번째 멤버 함수 ( `value`)를 사용 하 여 `_Where` 삽입 지점 검색 제어 되는 시퀀스 내의 시작 지점으로 합니다.  
  
 범위에서 요소 값의 시퀀스를 삽입 하는 세 번째 멤버 함수 [ `first`, `last`).  
  
 마지막 두 멤버 함수는 처음 두 함수와 똑같이 동작하지만, `value`는 삽입된 값을 생성하는데 사용된다는 점이 다릅니다.  
  
##  <a name="a-namekeyeqa-keyeq"></a><a name="key_eq"></a>key_eq 

 저장 된 같음 비교 함수 개체입니다.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>반환 값  
 저장 된 같음 비교 함수 개체입니다.  
  
##  <a name="a-nameloadfactora-loadfactor"></a><a name="load_factor"></a>load_factor 

 계산 하 고 컨테이너의 현재 로드 비율을 반환 합니다. 로드 비율에 버킷 수로 나눈 컨테이너의 요소 수입니다.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>반환 값  
 컨테이너에 대 한 로드 비율을 지정 합니다.  
  
##  <a name="a-namemaxloadfactora-maxloadfactor"></a><a name="max_load_factor"></a>max_load_factor 

 컨테이너의 최대 로드 비율을 가져오거나 설정 합니다. 최대 로드 비율 컨테이너 내부 테이블을 확장 하기 전에 모든 버킷의 수 있는 것 보다 요소의 최대 수는 있습니다.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Newmax`  
  
### <a name="return-value"></a>반환 값  
 첫 번째 멤버 함수는 저장된 최대 로드 비율을 반환합니다. 두 번째 멤버 함수 값을 반환 하지 않지만 throw는 [out_of_range](../../../standard-library/out-of-range-class.md) 제공 된 로드 비율을 유효 하지 않으면 예외...  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 할당자에 의해 결정 동시 컨테이너의 최대 크기를 반환 합니다. 이 방법은 동시성 안전 합니다.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 동시 컨테이너에 삽입 될 수 있는 요소의 최대 수입니다.  
  
### <a name="remarks"></a>주의  
 상한 값이 실제로 어떻게 컨테이너 실제로 보유할 수 보다 높은 수 있습니다.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>연산자 = 

 다른 할당 `concurrent_unordered_multiset` 여기에 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.  
  
```
concurrent_unordered_multiset& operator= (const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset& operator= (concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Uset`  
 소스 `concurrent_unordered_multiset` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `concurrent_unordered_multiset` 개체입니다.  
  
### <a name="remarks"></a>주의  
 순서가 지정되지 않은 multiset의 기존 요소를 지운 후에 `operator=`는 `_Uset`의 내용을 순서가 지정되지 않은 동시 multiset으로 복사하거나 이동합니다.  
  
##  <a name="a-namerehasha-rehash"></a><a name="rehash"></a>rehash 

 해시 테이블을 다시 빌드합니다.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Buckets`  
 원하는 버킷 수입니다.  
  
### <a name="remarks"></a>주의  
 멤버 함수는 필요에 따라 버킷 수를 `_Buckets` 이상으로 변경하고 해시 테이블을 다시 빌드합니다. 버킷 수는 2의 거듭제곱 이어야 합니다. 하지 2의 거듭제곱을 하는 경우 그 반올림 됩니다 다음 가장 큰 2의 제곱을 합니다.  
  
 Throw는 [out_of_range](../../../standard-library/out-of-range-class.md) 예외 버킷 수가 올바르지 않으면 (0 또는 최대 버킷 개수 보다 큰).  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>크기 

 이 동시 컨테이너의 요소 수를 반환합니다. 이 방법은 동시성 안전 합니다.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 컨테이너에 들어 있는 항목 수입니다.  
  
### <a name="remarks"></a>주의  
 동시 삽입이 있을 경우 이 함수를 호출한 직후, 반환 값을 읽기도 전에 동시 컨테이너의 요소 수가 변경될 수 있습니다.  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>스왑 

 두 개의의 내용을 바꿉니다 `concurrent_unordered_multiset` 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.  
  
```
void swap(concurrent_unordered_multiset& _Uset);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Uset`  
 스왑할 `concurrent_unordered_multiset` 개체입니다.  
  
##  <a name="a-nameunsafebegina-unsafebegin"></a><a name="unsafe_begin"></a>unsafe_begin 

 특정 버킷의 대 한이 컨테이너의 첫 번째 요소에 반복기를 반환합니다.  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷의 시작 부분을 가리키는 반복기입니다.  
  
##  <a name="a-nameunsafebucketa-unsafebucket"></a><a name="unsafe_bucket"></a>unsafe_bucket 

 특정 키가이 컨테이너에 매핑되는 버킷 인덱스를 반환 합니다.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 검색 중인 요소 키입니다.  
  
### <a name="return-value"></a>반환 값  
 이 컨테이너의 키에 대 한 버킷 인덱스입니다.  
  
##  <a name="a-nameunsafebucketcounta-unsafebucketcount"></a><a name="unsafe_bucket_count"></a>unsafe_bucket_count 

 이 컨테이너의 현재 버킷 수를 반환 합니다.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>반환 값  
 현재이 컨테이너의 버킷 수입니다.  
  
##  <a name="a-nameunsafebucketsizea-unsafebucketsize"></a><a name="unsafe_bucket_size"></a>unsafe_bucket_size 

 이 컨테이너의은 특정 버킷의 항목 수를 반환합니다.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 검색할 통 합니다.  
  
### <a name="return-value"></a>반환 값  
 현재이 컨테이너의 버킷 수입니다.  
  
##  <a name="a-nameunsafecbegina-unsafecbegin"></a><a name="unsafe_cbegin"></a>unsafe_cbegin 

 특정 버킷의 대 한이 컨테이너의 첫 번째 요소에 반복기를 반환합니다.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷의 시작 부분을 가리키는 반복기입니다.  
  
##  <a name="a-nameunsafecenda-unsafecend"></a><a name="unsafe_cend"></a>unsafe_cend 

 특정 버킷의에서 마지막 요소 다음의 위치는 반복기를 반환 합니다.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷의 시작 부분을 가리키는 반복기입니다.  
  
##  <a name="a-nameunsafeenda-unsafeend"></a><a name="unsafe_end"></a>unsafe_end 

 특정 버킷의 대 한이 컨테이너의 마지막 요소에 반복기를 반환합니다.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷의 끝을 가리키는 반복기입니다.  
  
##  <a name="a-nameunsafeerasea-unsafeerase"></a><a name="unsafe_erase"></a>unsafe_erase 

 요소를 제거는 `concurrent_unordered_multiset` 지정 된 위치에 있습니다. 이 메서드는 동시성이 보장 되지 않습니다.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);

size_type unsafe_erase(
    const key_type& KVal);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Where`  
 반복기의 위치는에서 지우기입니다.  
  
 `first`  
 `last`  
 `KVal`  
 지울 키 값입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 두 멤버 함수, 제거 된 요소에 남아 있는 첫 번째 요소를 지정 하는 반복기를 반환 합니다. 또는 [메서드 종료](#end)이러한 요소가 없는 경우 (). 세 번째 멤버 함수를 제거 하는 요소의 수를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 가 가리키는 요소를 제거 하는 첫 번째 멤버 함수 `_Where`합니다. 두 번째 멤버 함수 범위에서 요소 제거 [ `_Begin`, `_End`).  
  
 구분 된 범위의의 요소를 제거 하는 세 번째 멤버 함수 [equal_range 메서드](#equal_range)(KVal).  
  
##  <a name="a-nameunsafemaxbucketcounta-unsafemaxbucketcount"></a><a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 이 컨테이너의 최대 버킷 개수를 반환 합니다.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 컨테이너의 버킷 최대 수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)




