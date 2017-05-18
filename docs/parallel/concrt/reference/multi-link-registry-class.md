---
title: "multi_link_registry 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b52ee20ed16a4ce8d0b9f11b6acf25112464b49b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="multilinkregistry-class"></a>multi_link_registry 클래스
`multi_link_registry` 개체는 여러 소스 블록 또는 여러 대상 블록을 관리하는 `network_link_registry`입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Block`  
 블록 데이터 형식에 저장 되는 `multi_link_registry` 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|`multi_link_registry` 개체를 생성합니다.|  
|[~ multi_link_registry 소멸자](#dtor)|소멸은 `multi_link_registry` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[add](#add)|추가에 대 한 링크는 `multi_link_registry` 개체입니다. (재정의 [network_link_registry:: add](network-link-registry-class.md#add).)|  
|[begin](#begin)|첫 번째 요소에 반복기를 반환 합니다.는 `multi_link_registry` 개체입니다. (재정의 [network_link_registry:: begin](network-link-registry-class.md#begin).)|  
|[포함](#contains)|검색 된 `multi_link_registry` 지정된 된 블록에 대 한 개체입니다. (재정의 [network_link_registry:: contains](network-link-registry-class.md#contains).)|  
|[count](#count)|에 있는 항목의 개수는 `multi_link_registry` 개체입니다. (재정의 [network_link_registry:: count](network-link-registry-class.md#count).)|  
|[remove](#remove)|링크를 제거는 `multi_link_registry` 개체입니다. (재정의 [network_link_registry:: remove](network-link-registry-class.md#remove).)|  
|[set_bound](#set_bound)|링크의 수에 대 한 상한을 설정의 `multi_link_registry` 개체가 보유할 수 있습니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="add"></a>추가 

 추가에 대 한 링크는 `multi_link_registry` 개체입니다.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 추가할 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 메서드에서 throw 한 [invalid_link_target](invalid-link-target-class.md) 예외 링크 레지스트리에 이미 있습니다. 또는 바인딩된 경우 이미 설정 되어 있는 `set_bound` 함수 및 링크 하므로 제거 되었습니다.  
  
##  <a name="begin"></a>시작 

 첫 번째 요소에 반복기를 반환 합니다.는 `multi_link_registry` 개체입니다.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소를 주소 지정 하는 반복기는 `multi_link_registry` 개체입니다.  
  
### <a name="remarks"></a>주의  
 최종 상태 하 여 표시 되는 `NULL` 링크 합니다.  
  
##  <a name="contains"></a>포함 

 검색 된 `multi_link_registry` 지정된 된 블록에 대 한 개체입니다.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 검색 한 블록에 대 한 포인터는 `multi_link_registry` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`지정한 블록이 있으면 `false` 그렇지 않은 경우.  
  
##  <a name="count"></a>개수 

 에 있는 항목의 개수는 `multi_link_registry` 개체입니다.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>반환 값  
 항목 수는 `multi_link_registry` 개체입니다.  
  
##  <a name="ctor"></a>multi_link_registry 

 `multi_link_registry` 개체를 생성합니다.  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a>~ multi_link_registry 

 소멸은 `multi_link_registry` 개체입니다.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>설명  
 메서드에서 throw 한 [invalid_operation](invalid-operation-class.md) 모든 링크가 제거 되기 전에 호출 된 경우에 예외입니다.  
  
##  <a name="remove"></a>제거 

 링크를 제거는 `multi_link_registry` 개체입니다.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `true`링크를 찾아 제거 했으면 `false` 그렇지 않은 경우.  
  
##  <a name="set_bound"></a>set_bound 

 링크의 수에 대 한 상한을 설정의 `multi_link_registry` 개체가 보유할 수 있습니다.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MaxLinks`  
 최대 수 있는 링크는 `multi_link_registry` 개체가 보유할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 한도가 설정된 후 항목의 연결을 해제하면 `multi_link_registry` 개체가 변경 불가능한 상태로 전환됩니다. 이 상태에서 `add`를 추가로 호출하면 `invalid_link_target` 예외가 throw됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [single_link_registry 클래스](single-link-registry-class.md)

