---
title: concurrent_unordered_set 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::hash_function
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::insert
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::key_eq
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::swap
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::unsafe_erase
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_set class
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd73b16725cfe4b30734673bb926d104af0d3264
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694695"
---
# <a name="concurrentunorderedset-class"></a>concurrent_unordered_set 클래스
`concurrent_unordered_set` 클래스는 다양 한 길이의 K. 형식의 요소 시퀀스를 제어 하는 동시성 으로부터 안전한 컨테이너 시퀀스는 동시성 으로부터 안전한 방식으로 표시 됩니다 추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_set : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
 _Hasher,
    key_equality>,
 _Allocator_type,
    false>>;
```   
  
#### <a name="parameters"></a>매개 변수  
 `K`  
 키 형식입니다.  
  
 `_Hasher`  
 해시 함수 개체 형식입니다. 이 인수는 선택 사항이며 기본값은 `std::hash<K>`입니다.  
  
 `key_equality`  
 같음 비교 함수 개체 형식입니다. 이 인수는 선택 사항이며 기본값은 `std::equal_to<K>`입니다.  
  
 `_Allocator_type`  
 할당 및 순서가 지정 되지 않은 동시 집합에 대 한 메모리 할당 취소에 대 한 세부 정보를 캡슐화 하는 저장 된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `std::allocator<K>`입니다.  
  
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
|[concurrent_unordered_set](#ctor)|오버로드됨. 순서가 지정 되지 않은 동시 집합을 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[hash_function](#hash_function)|저장 된 해시 함수 개체를 반환 합니다.|  
|[insert](#insert)|오버로드됨. 요소를 추가 하 고 `concurrent_unordered_set` 개체입니다.|  
|[key_eq](#key_eq)|저장 된 같음 비교 함수 개체를 반환합니다.|  
|[swap](#swap)|두 개의의 내용을 바꿉니다 `concurrent_unordered_set` 개체입니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
|[unsafe_erase](#unsafe_erase)|오버로드됨. 요소 제거는 `concurrent_unordered_set` 지정 된 위치에 있습니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator=](#operator_eq)|오버로드됨. 다른 할당 `concurrent_unordered_set` 여기에 개체입니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
  
## <a name="remarks"></a>설명  
 에 대 한 자세한 내용은 `concurrent_unordered_set` 클래스를 참조 하십시오. [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concurrent_unordered_set.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="begin"></a> 시작 

 동시 컨테이너의 첫 번째 요소를 가리키는 반복기를 반환 합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 첫 번째 요소는 반복기입니다.  
  
##  <a name="cbegin"></a> cbegin 

 동시 컨테이너의 첫 번째 요소를 가리키는 상수 반복기를 반환 합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 첫 번째 요소에는 const 반복기입니다.  
  
##  <a name="cend"></a> cend 

 동시 컨테이너의 마지막 요소 다음에 나오는 위치를 가리키는 상수 반복기를 반환 합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 마지막 요소 다음 위치에는 const 반복기입니다.  
  
##  <a name="clear"></a> 지우기 

 동시 컨테이너의 모든 요소를 지웁니다. 이 함수는 동시성 안전 하지 않습니다.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_unordered_set 

 순서가 지정 되지 않은 동시 집합을 만듭니다.  
  
```
explicit concurrent_unordered_set(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_set(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset);

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_set(
    concurrent_unordered_set&& _Uset);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Iterator`  
 입력 반복기의 형식입니다.  
  
 `_Number_of_buckets`  
 순서가 지정되지 않은 이 집합에 대한 초기 버킷 수입니다.  
  
 `_Hasher`  
 순서가 지정되지 않은 이 집합에 대한 해시 함수입니다.  
  
 `key_equality`  
 순서가 지정되지 않은 이 집합에 대한 같음 비교 함수입니다.  
  
 `_Allocator`  
 순서가 지정되지 않은 이 집합에 대한 할당자입니다.  
  
 `first`  
 `last`  
 `_Uset`  
 요소를 복사해 오거나 이동해 올 소스 `concurrent_unordered_set` 개체입니다.  
  
### <a name="remarks"></a>설명  
 모든 생성자는 할당자 개체 `_Allocator`를 저장하고 순서가 지정되지 않은 집합을 초기화합니다.  
  
 첫 번째 생성자는 비어 있는 초기 집합을 지정하고 사용할 버킷 수, 해시 함수, 같음 함수 및 할당자 형식을 명시적으로 지정합니다.  
  
 두 번째 생성자는 순서가 지정되지 않은 집합에 대한 할당자를 지정합니다.  
  
 세 번째 생성자는 반복기 범위에서 제공 하는 값을 지정 [ `_Begin`, `_End`).  
  
 네 번째 및 다섯 번째 생성자는 순서가 지정되지 않은 동시 집합 `_Uset`의 복사본을 지정합니다.  
  
 마지막 생성자는 순서가 지정되지 않은 동시 집합 `_Uset`의 이동을 지정합니다.  
  
##  <a name="count"></a> 개수 

 지정 된 키와 일치 하는 요소의 수를 계산 합니다. 이 함수는 동시성을 안전 하 게 보호 합니다.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 검색할 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키 컨테이너에 나타나는 횟수 시간.  
  
##  <a name="empty"></a> 빈 

 요소가 있는지 여부를 테스트합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 `true` 동시 컨테이너 비어 있으면 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 동시 삽입 있는 경우 동시 컨테이너 비어 여부 반환 값을 읽기도 전에이 함수를 호출한 직후 변경 될 수 있습니다.  
  
##  <a name="end"></a> 끝 

 동시 컨테이너의 마지막 요소 다음에 나오는 위치를 가리키는 반복기를 반환 합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 컨테이너의 마지막 요소 다음 위치에 사용 되는 반복기입니다.  
  
##  <a name="equal_range"></a> equal_range 

 지정된 된 키와 일치 하는 범위를 찾습니다. 이 함수는 동시성을 안전 하 게 보호 합니다.  
  
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
 검색할 키 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A [쌍](http://msdn.microsoft.com/en-us/32e72d66-3020-4cb9-92c3-f7a5fa7998ff) 여기서 첫 번째 요소는 시작 부분에 대 한 반복기 하 고 두 번째 요소는 반복기가 범위 끝에 있습니다.  
  
### <a name="remarks"></a>설명  
 Begin 반복기 뒤와 끝 반복기 앞에 삽입할 추가 키를 동시 삽입에 대 한 것 같습니다.  
  
##  <a name="find"></a> 찾기 

 지정된 키와 일치하는 요소를 찾습니다. 이 함수는 동시성을 안전 하 게 보호 합니다.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 검색할 키 값입니다.  
  
### <a name="return-value"></a>반환 값  
 위치를 가리키는 반복기는 첫 번째 요소를 제공 하는 키를 일치 하는 또는 반복기 `end()` 이러한 요소가 없을 경우.  
  
##  <a name="get_allocator"></a> get_allocator 

 이 동시 컨테이너에 대 한 저장 된 할당자 개체를 반환합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 동시 컨테이너에 대해 저장 된 할당자 개체입니다.  
  
##  <a name="hash_function"></a> hash_function 

 저장 된 해시 함수 개체를 반환 합니다.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>반환 값  
 저장된 해시 함수 개체입니다.  
  
##  <a name="insert"></a> 삽입 

 요소를 추가 하 고 `concurrent_unordered_set` 개체입니다.  
  
```
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
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
 Set에 삽입 된 값의 형식입니다.  
  
 `value`  
 삽입할 값입니다.  
  
 `_Where`  
 삽입 지점을 검색할 시작 위치입니다.  
  
 `first`  
 삽입할 범위의 시작 부분입니다.  
  
 `last`  
 삽입할 범위의 끝입니다.  
  
### <a name="return-value"></a>반환 값  
 반복기 및 부울 값을 포함 하는 쌍입니다. 자세한 내용은 설명 섹션을 참조 하십시오.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수 X 요소 키의 순서 지정이 동일할가 시퀀스에 있는지 여부를 결정 `value`합니다. Not, 이러한 요소 X 만들고으로 초기화 하는 경우 `value`합니다. 함수에는 다음 반복기 결정 `where` X를 지정 하는 합니다. 함수 반환 삽입 발생 한 `std::pair(where, true)`합니다. 그 외의 경우 `std::pair(where, false)`를 반환합니다.  
  
 삽입을 반환 하는 두 번째 멤버 함수 ( `value`)를 사용 하 여 `_Where` 삽입 지점 검색 제어 되는 시퀀스 내의 시작 위치로 합니다.  
  
 범위에서 요소 값의 시퀀스를 삽입 하는 세 번째 멤버 함수 [ `first`, `last`).  
  
 마지막 두 멤버 함수는 처음 두 함수와 똑같이 동작하지만, `value`는 삽입된 값을 생성하는데 사용된다는 점이 다릅니다.  
  
##  <a name="key_eq"></a> key_eq 

 저장 된 같음 비교 함수 개체를 반환합니다.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>반환 값  
 저장 된 같음 비교 함수 개체입니다.  
  
##  <a name="load_factor"></a> load_factor 

 계산 하 고 컨테이너의 현재 로드 비율을 반환 합니다. 로드 비율은 버킷 수로 나눈 컨테이너에 있는 요소의 수입니다.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>반환 값  
 컨테이너에 대 한 로드 비율입니다.  
  
##  <a name="max_load_factor"></a> max_load_factor 

 컨테이너의 최대 로드 비율을 가져오거나 설정 합니다. 최대 로드 비율 컨테이너 내부 테이블에 맞게 증가 하기 전에 모든 버킷의 수 있는 것 보다 요소의 최대 수는 있습니다.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Newmax`  
  
### <a name="return-value"></a>반환 값  
 첫 번째 멤버 함수는 저장된 최대 로드 비율을 반환합니다. 두 번째 멤버 함수 값을 반환 하지 않지만 throw 한 [out_of_range](../../../standard-library/out-of-range-class.md) 예외는 제공 된 로드 비율 유효 하지 않을 경우...  
  
##  <a name="max_size"></a> max_size 

 할당자에 의해 결정 동시 컨테이너의 최대 크기를 반환 합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 동시 컨테이너에 삽입 될 수 있는 요소의 최대 수입니다.  
  
### <a name="remarks"></a>설명  
 상한 값이 실제로 컨테이너 저장할 실제로 수 있는 내용 보다 더 높은 수 있습니다.  
  
##  <a name="operator_eq"></a> 연산자 = 

 다른 할당 `concurrent_unordered_set` 여기에 개체입니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
concurrent_unordered_set& operator= (const concurrent_unordered_set& _Uset);

concurrent_unordered_set& operator= (concurrent_unordered_set&& _Uset);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Uset`  
 소스 `concurrent_unordered_set` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `concurrent_unordered_set` 개체입니다.  
  
### <a name="remarks"></a>설명  
 `operator=`는 순서가 지정되지 않은 동시 집합에서 기존 요소를 지운 다음 이 집합으로 `_Uset`의 내용을 이동하거나 복사합니다.  
  
##  <a name="rehash"></a> rehash 

 해시 테이블을 다시 빌드합니다.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Buckets`  
 원하는 버킷 수입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 필요에 따라 버킷 수를 `_Buckets` 이상으로 변경하고 해시 테이블을 다시 빌드합니다. 버킷 수는 2의 거듭제곱 이어야 합니다. 경우 하지 2의 거듭제곱을 다음 가장 큰 2의 제곱을 반올림 됩니다 됩니다.  
  
 throw 한 [out_of_range](../../../standard-library/out-of-range-class.md) 버킷 수가 유효 하지 않을 경우 예외 (0 또는 최대 버킷 개수 보다 큰).  
  
##  <a name="size"></a> 크기 

 이 동시 컨테이너의 요소 수를 반환합니다. 이 방법은 안전 하 게 보호 되는 동시성에 설명 합니다.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>반환 값  
 컨테이너에 들어 있는 항목 수입니다.  
  
### <a name="remarks"></a>설명  
 동시 삽입이 있을 경우 이 함수를 호출한 직후, 반환 값을 읽기도 전에 동시 컨테이너의 요소 수가 변경될 수 있습니다.  
  
##  <a name="swap"></a> 스왑 

 두 개의의 내용을 바꿉니다 `concurrent_unordered_set` 개체입니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
void swap(concurrent_unordered_set& _Uset);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Uset`  
 스왑할 `concurrent_unordered_set` 개체입니다.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

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
  
##  <a name="unsafe_bucket"></a> unsafe_bucket 

 특정 키가이 컨테이너에 매핑되는 버킷 인덱스를 반환 합니다.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `KVal`  
 검색 중인 요소 키입니다.  
  
### <a name="return-value"></a>반환 값  
 이 컨테이너의 키에 대 한 버킷 인덱스입니다.  
  
##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count 

 이 컨테이너의 현재 버킷 수를 반환합니다.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>반환 값  
 현재이 컨테이너의 버킷 수입니다.  
  
##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size 

 이 컨테이너의은 특정 버킷의 항목 수를 반환합니다.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 검색할 버킷입니다.  
  
### <a name="return-value"></a>반환 값  
 현재이 컨테이너의 버킷 수입니다.  
  
##  <a name="unsafe_cbegin"></a> unsafe_cbegin 

 특정 버킷의 대 한이 컨테이너의 첫 번째 요소에 반복기를 반환합니다.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷의 시작 부분을 가리키는 반복기입니다.  
  
##  <a name="unsafe_cend"></a> unsafe_cend 

 특정 버킷의 마지막 요소 다음 위치에는 반복기를 반환 합니다.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷의 시작 부분을 가리키는 반복기입니다.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 특정 버킷의 대 한이 컨테이너의 마지막 요소에 반복기를 반환합니다.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Bucket`  
 버킷 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 버킷 끝의를 가리키는 반복기입니다.  
  
##  <a name="unsafe_erase"></a> unsafe_erase 

 요소 제거는 `concurrent_unordered_set` 지정 된 위치에 있습니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

size_type unsafe_erase(
    const key_type& KVal);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Where`  
 반복기의 위치는에서 지우기입니다.  
  
 `KVal`  
 지우기 키 값입니다.  
  
 `first`  
 `last`  
  
### <a name="return-value"></a>반환 값  
 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 하는 처음 두 멤버 함수 또는 [끝](#end)이러한 요소가 없을 경우 (). 세 번째 멤버 함수를 제거 하는 요소의 수를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 가 가리키는 요소를 제거 하는 첫 번째 멤버 함수 `_Where`합니다. 두 번째 멤버 함수 범위에서 요소 제거 [ `_Begin`, `_End`).  
  
 구분 된 범위의 요소를 제거 하는 세 번째 멤버 함수 [equal_range](#equal_range)(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count 

 이 컨테이너의 최대 버킷 개수를 반환합니다.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 컨테이너의 버킷 최대 수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)



