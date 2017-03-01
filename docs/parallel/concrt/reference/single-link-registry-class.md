---
title: "single_link_registry 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::single_link_registry
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 3f4719881fac882611f68b36d410c0611f99ba01
ms.lasthandoff: 02/24/2017

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
|[single_link_registry 생성자](#ctor)|`single_link_registry` 개체를 생성합니다.|  
|[~ single_link_registry 소멸자](#dtor)|소멸은 `single_link_registry` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[메서드 추가](#add)|추가에 대 한 링크는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: add](network-link-registry-class.md#add).)|  
|[begin 메서드](#begin)|첫 번째 요소에 반복기를 반환 합니다.는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: begin](network-link-registry-class.md#begin).)|  
|[메서드를 포함합니다.](#contains)|검색 된 `single_link_registry` 지정된 된 블록에 대 한 개체입니다. (재정의 [network_link_registry:: contains](network-link-registry-class.md#contains).)|  
|[count 메서드](#count)|에 있는 항목의 개수는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: count](network-link-registry-class.md#count).)|  
|[remove 메서드](#remove)|링크를 제거는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>추가 

 추가에 대 한 링크는 `single_link_registry` 개체입니다.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 추가할 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_link_target](invalid-link-target-class.md) 이미 링크에에서 있으면이 레지스트리는 예외입니다.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>시작 

 첫 번째 요소에 반복기를 반환 합니다.는 `single_link_registry` 개체입니다.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소를 주소 지정 하는 반복기는 `single_link_registry` 개체입니다.  
  
### <a name="remarks"></a>주의  
 최종 상태 하 여 표시 되는 `NULL` 링크 합니다.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>포함 

 검색 된 `single_link_registry` 지정된 된 블록에 대 한 개체입니다.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 검색 한 블록에 대 한 포인터는 `single_link_registry` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`링크를 찾을 수 있으면 `false` 그렇지 않은 경우.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>개수 

 에 있는 항목의 개수는 `single_link_registry` 개체입니다.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>반환 값  
 항목 수는 `single_link_registry` 개체입니다.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>제거 

 링크를 제거는 `single_link_registry` 개체입니다.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `true`링크를 찾아 제거 했으면 `false` 그렇지 않은 경우.  
  
##  <a name="a-namectora-singlelinkregistry"></a><a name="ctor"></a>single_link_registry 

 `single_link_registry` 개체를 생성합니다.  
  
```
single_link_registry();
```  
  
##  <a name="a-namedtora-singlelinkregistry"></a><a name="dtor"></a>~ single_link_registry 

 소멸은 `single_link_registry` 개체입니다.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_operation](invalid-operation-class.md) 링크를 제거 하기 전에 메서드를 호출 하는 예외입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [multi_link_registry 클래스](multi-link-registry-class.md)

