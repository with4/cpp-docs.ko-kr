---
title: concurrent_queue 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
dev_langs:
- C++
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9a3ee82b8b81532b4e63f080ad321a93725ce41
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693122"
---
# <a name="concurrentqueue-class"></a>concurrent_queue 클래스
`concurrent_queue` 클래스는 해당 요소에 대해 선입 선출 액세스를 허용하는 시퀀스 컨테이너 클래스입니다. `push` 및 `try_pop`과 같은 동시성으로부터 안전한 작업의 제한된 집합을 사용할 수 있게 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 큐에 저장 될 요소의 데이터 형식입니다.  
  
 `_Ax`  
 할당 및이 동시 큐에 대 한 메모리 할당 취소에 대 한 세부 정보를 캡슐화 하는 저장 된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `allocator<T>`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`allocator_type`|동시 큐에 대 한 할당자 클래스를 나타내는 형식입니다.|  
|`const_iterator`|비-스레드로부터 안전한을 나타내는 형식을 `const` 동시 큐에 요소를 마우스로 반복기입니다.|  
|`const_reference`|에 대 한 참조를 제공 하는 형식은 `const` 읽고 수행 하기 위해 동시 큐에 저장 된 요소 `const` 작업 합니다.|  
|`difference_type`|동시 큐에 두 요소 사이의 부호가 있는 거리를 제공 하는 형식입니다.|  
|`iterator`|동시 큐에 요소를 마우스로 스레드로부터 안전 하지 않은 반복기를 나타내는 형식입니다.|  
|`reference`|동시 큐에 저장 된 요소에 대 한 참조를 제공 하는 형식입니다.|  
|`size_type`|동시 큐에 있는 요소의 수를 계산 하는 형식입니다.|  
|`value_type`|동시 큐에 저장 된 데이터 형식을 나타내는 형식입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|오버로드됨. 동시 큐를 생성 합니다.|  
|[~ concurrent_queue 소멸자](#dtor)|동시 큐를 제거합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[clear](#clear)|동시 큐를 파괴 지웁니다 현재 큐에 배치 된 요소입니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
|[empty](#empty)|이 메서드가 호출 될 때 현재 동시 큐가 비어 있는지 테스트 합니다. 이 메서드는 동시성 으로부터 안전한.|  
|[get_allocator](#get_allocator)|동시 큐를 생성 하는 데 사용 되는 할당자 복사본을 반환 합니다. 이 메서드는 동시성 으로부터 안전한.|  
|[push](#push)|오버로드됨. 동시 큐의 비상 로그에 있는 항목 큐에 넣습니다. 이 메서드는 동시성 으로부터 안전한.|  
|[try_pop](#try_pop)|사용 가능한 경우 큐에서 항목을 제거 합니다. 이 메서드는 동시성 으로부터 안전한.|  
|[unsafe_begin](#unsafe_begin)|오버로드됨. 형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 큐의 시작 부분에 있습니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
|[unsafe_end](#unsafe_end)|오버로드됨. 형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 큐의 끝에 있습니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
|[unsafe_size](#unsafe_size)|큐에 있는 항목의 수를 반환합니다. 이 메서드는 동시성 으로부터 안전한 없습니다.|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `concurrent_queue`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concurrent_queue.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="clear"></a> 지우기 

 동시 큐를 파괴 지웁니다 현재 큐에 배치 된 요소입니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_queue 

 동시 큐를 생성 합니다.  
  
```
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>매개 변수  
 `_InputIterator`  
 값의 범위를 지정 하는 입력된 반복기의 형식입니다.  
  
 `_Al`  
 이 개체에 사용할 할당자 클래스입니다.  
  
 `_OtherQ`  
 요소를 복사해 오거나 이동해 올 소스 `concurrent_queue` 개체입니다.  
  
 `_Begin`  
 복사할 요소의 범위에서 첫 번째 요소의 위치입니다.  
  
 `_End`  
 복사할 요소의 범위를 벗어난 첫 번째 요소의 위치입니다.  
  
### <a name="remarks"></a>설명  
 모든 생성자는 할당자 개체를 저장할 `_Al` 는 큐를 초기화 합니다.  
  
 첫 번째 생성자는 비어 있는 초기 큐를 지정 하 고 사용할 할당자 형식을 명시적으로 지정 합니다.  
  
 동시 큐의 복사본을 지정 하는 두 번째 생성자는 `_OtherQ`합니다.  
  
 세 번째 생성자는 동시 큐 `_OtherQ`의 이동을 지정합니다.  
  
 반복기 범위에서 제공 하는 값을 지정 하는 네 번째 생성자는 [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~concurrent_queue 

 동시 큐를 제거합니다.  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a> 빈 

 이 메서드가 호출 될 때 현재 동시 큐가 비어 있는지 테스트 합니다. 이 메서드는 동시성 으로부터 안전한.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>반환 값  
 `true` 순간에 동시 큐가 비어 있으면 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 이 메서드는 동시성 으로부터 안전한 동안 메서드 호출에 대해 `push`, `try_pop`, 및 `empty`, 반환 되는 값 올바르지 않을 호출 스레드에 의해 검사 되는 시점입니다.  
  
##  <a name="get_allocator"></a> get_allocator 

 동시 큐를 생성 하는 데 사용 되는 할당자 복사본을 반환 합니다. 이 메서드는 동시성 으로부터 안전한.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 큐를 생성 하는 데 사용 되는 할당자 복사본입니다.  
  
##  <a name="push"></a> 푸시 

 동시 큐의 비상 로그에 있는 항목 큐에 넣습니다. 이 메서드는 동시성 으로부터 안전한.  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
 큐에 추가할 항목입니다.  
  
### <a name="remarks"></a>설명  
 `push` 동시성 으로부터 안전한은 메서드 호출에 대해 `push`, `try_pop`, 및 `empty`합니다.  
  
##  <a name="try_pop"></a> try_pop 

 사용 가능한 경우 큐에서 항목을 제거 합니다. 이 메서드는 동시성 으로부터 안전한.  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 큐에서 제거 된 항목을 저장할 위치에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 항목이 성공적으로 큐에서 제거 되었으면 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 항목이 성공적으로 큐에서 제거 된 경우 매개 변수 `_Dest` 큐에서 제거 된 값을 받는 큐에 저장 된 원래 값을 제거 하 고이 함수는 반환 `true`합니다. 이 함수를 반환 하는 경우 큐에서 제거할 대상 항목이 했습니다, `false` 내용의 차단 없이 `_Dest` 매개 변수가 정의 되지 않습니다.  
  
 `try_pop` 동시성 으로부터 안전한은 메서드 호출에 대해 `push`, `try_pop`, 및 `empty`합니다.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 큐의 시작 부분에 있습니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>반환 값  
 반복기 형식의 `iterator` 또는 `const_iterator` 동시 큐 개체의 시작 부분에 있습니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 반복기의 `concurrent_queue` 클래스는 디버깅을 위해 주로 느리기와 반복은 동시성 으로부터 안전한 다른 큐 작업에 관해 되지 않습니다.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 큐의 끝에 있습니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>반환 값  
 반복기 형식의 `iterator` 또는 `const_iterator` 동시 큐의 끝에 있습니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 반복기의 `concurrent_queue` 클래스는 디버깅을 위해 주로 느리기와 반복은 동시성 으로부터 안전한 다른 큐 작업에 관해 되지 않습니다.  
  
##  <a name="unsafe_size"></a> unsafe_size 

 큐에 있는 항목의 수를 반환합니다. 이 메서드는 동시성 으로부터 안전한 없습니다.  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>반환 값  
 동시 큐의 크기입니다.  
  
### <a name="remarks"></a>설명  
 `unsafe_size` 동시성 으로부터 안전한 아니며 잘못 된 경우 결과가 메서드에 대 한 호출을 동시에 호출할 `push`, `try_pop`, 및 `empty`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
