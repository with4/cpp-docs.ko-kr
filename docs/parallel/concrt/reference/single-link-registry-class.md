---
title: single_link_registry 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3220156d201a4dcb7edb6281298d3f248f38fc83
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690028"
---
# <a name="singlelinkregistry-class"></a>single_link_registry 클래스
`single_link_registry` 개체는 단일 소스 또는 대상 블록만 관리하는 `network_link_registry`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Block`  
 블록 데이터 형식에 저장 되는 `single_link_registry` 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[single_link_registry](#ctor)|`single_link_registry` 개체를 생성합니다.|  
|[~ single_link_registry 소멸자](#dtor)|소멸 된 `single_link_registry` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[add](#add)|한 링크를 추가 하는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: add](network-link-registry-class.md#add).)|  
|[begin](#begin)|첫 번째 요소에 반복기를 반환 합니다.는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: begin](network-link-registry-class.md#begin).)|  
|[포함](#contains)|검색 된 `single_link_registry` 지정된 된 블록에 대 한 개체입니다. (재정의 [network_link_registry:: contains](network-link-registry-class.md#contains).)|  
|[count](#count)|에 있는 항목의 개수는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: count](network-link-registry-class.md#count).)|  
|[remove](#remove)|링크를 제거는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="add"></a> 추가 

 한 링크를 추가 하는 `single_link_registry` 개체입니다.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 추가할 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 된 [invalid_link_target](invalid-link-target-class.md) 이미 있는 경우 링크에서 레지스트리를 이와이 같이 예외입니다.  
  
##  <a name="begin"></a> 시작 

 첫 번째 요소에 반복기를 반환 합니다.는 `single_link_registry` 개체입니다.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소를 주소 지정 하는 반복기는 `single_link_registry` 개체입니다.  
  
### <a name="remarks"></a>설명  
 최종 상태도 표시 됩니다는 `NULL` 링크 합니다.  
  
##  <a name="contains"></a> 포함 

 검색 된 `single_link_registry` 지정된 된 블록에 대 한 개체입니다.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 에 대 한 검색할 블록에 대 한 포인터는 `single_link_registry` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 링크를 찾을 수 있으면 `false` 그렇지 않은 경우.  
  
##  <a name="count"></a> 개수 

 에 있는 항목의 개수는 `single_link_registry` 개체입니다.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>반환 값  
 항목 수는 `single_link_registry` 개체입니다.  
  
##  <a name="remove"></a> 제거 

 링크를 제거는 `single_link_registry` 개체입니다.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 링크를 찾아 제거 했으면 `false` 그렇지 않은 경우.  
  
##  <a name="ctor"></a> single_link_registry 

 `single_link_registry` 개체를 생성합니다.  
  
```
single_link_registry();
```  
  
##  <a name="dtor"></a> ~single_link_registry 

 소멸 된 `single_link_registry` 개체입니다.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 한 [invalid_operation](invalid-operation-class.md) 예외 링크를 제거 하기 전에 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [multi_link_registry 클래스](multi-link-registry-class.md)
