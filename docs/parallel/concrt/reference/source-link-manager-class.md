---
title: "source_link_manager 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_link_manager
dev_langs:
- C++
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
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
ms.openlocfilehash: b9323da4d2ccefe09ba38df088e546828d41f2ee
ms.lasthandoff: 02/24/2017

---
# <a name="sourcelinkmanager-class"></a>source_link_manager 클래스
`source_link_manager` 개체는 `ISource` 블록에 대한 메시징 블록 네트워크 연결을 관리합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>매개 변수  
 `_LinkRegistry`  
 네트워크 연결 레지스트리입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`const_pointer`|에 대 한 포인터를 제공 하는 형식은 `const` 요소에는 `source_link_manager` 개체입니다.|  
|`const_reference`|에 대 한 참조를 제공 하는 형식은 `const` 에 저장 된 요소는 `source_link_manager` 읽고 const 작업을 수행 하기 위해 개체입니다.|  
|`iterator`|반복기를 제공 하는 형식 읽거나에 있는 모든 요소를 수정할 수는 `source_link_manager` 개체입니다.|  
|`type`|관리 되는 링크 레지스트리 유형의 `source_link_manager` 개체입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[source_link_manager 생성자](#ctor)|`source_link_manager` 개체를 생성합니다.|  
|[~ source_link_manager 소멸자](#dtor)|소멸은 `source_link_manager` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[메서드 추가](#add)|소스 링크를 추가 하는 `source_link_manager` 개체입니다.|  
|[begin 메서드](#begin)|첫 번째 요소에 반복기를 반환 합니다.는 `source_link_manager` 개체입니다.|  
|[메서드를 포함합니다.](#contains)|검색 된 `network_link_registry` 이 `source_link_manager` 지정된 된 블록에 대 한 개체입니다.|  
|[count 메서드](#count)|에 연결 된 블록의 개수는 `source_link_manager` 개체입니다.|  
|[메서드 참조](#reference)|에 대 한 참조를 얻습니다는 `source_link_manager` 개체입니다.|  
|[register_target_block 메서드](#register_target_block)|이 보유 하는 대상 블록을 등록 `source_link_manager` 개체입니다.|  
|[release 메서드](#release)|참조를 해제는 `source_link_manager` 개체입니다.|  
|[remove 메서드](#remove)|링크를 제거는 `source_link_manager` 개체입니다.|  
|[set_bound 메서드](#set_bound)|이에 추가할 수 있는 소스 링크의 최대 수를 설정 `source_link_manager` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 현재 소스 블록에는 참조 횟수가 계산 됩니다. 이 래퍼는 `network_link_registry` 링크에 대 한 동시 액세스 가능 하며 콜백을 통해 링크를 참조 하는 기능을 제공 하는 개체입니다. 메시지 블록 ( `target_block`s 또는 `propagator_block`s)은 소스 연결에 대 한이 클래스를 사용 해야 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `source_link_manager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>추가 

 소스 링크를 추가 하는 `source_link_manager` 개체입니다.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 추가할 블록에 대 한 포인터입니다.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>시작 

 첫 번째 요소에 반복기를 반환 합니다.는 `source_link_manager` 개체입니다.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 요소를 주소 지정 하는 반복기는 `source_link_manager` 개체입니다.  
  
### <a name="remarks"></a>주의  
 반복기의 최종 상태도 표시 됩니다는 `NULL` 링크 합니다.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>포함 

 검색 된 `network_link_registry` 이 `source_link_manager` 지정된 된 블록에 대 한 개체입니다.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 검색 한 블록에 대 한 포인터는 `source_link_manager` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`지정한 블록이 있으면 `false` 그렇지 않은 경우.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>개수 

 에 연결 된 블록의 개수는 `source_link_manager` 개체입니다.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>반환 값  
 에 연결 된 블록 수는 `source_link_manager` 개체입니다.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>참조 

 에 대 한 참조를 얻습니다는 `source_link_manager` 개체입니다.  
  
```
void reference();
```  
  
##  <a name="a-nameregistertargetblocka-registertargetblock"></a><a name="register_target_block"></a>register_target_block 

 이 보유 하는 대상 블록을 등록 `source_link_manager` 개체입니다.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PTarget`  
 이 보유 하는 대상 블록 `source_link_manager` 개체입니다.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>릴리스 

 참조를 해제는 `source_link_manager` 개체입니다.  
  
```
void release();
```  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>제거 

 링크를 제거는 `source_link_manager` 개체입니다.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Link`  
 제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `true`링크를 찾아 제거 했으면 `false` 그렇지 않은 경우.  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 이에 추가할 수 있는 소스 링크의 최대 수를 설정 `source_link_manager` 개체입니다.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>매개 변수  
 `_MaxLinks`  
 링크의 최대 수입니다.  
  
##  <a name="a-namectora-sourcelinkmanager"></a><a name="ctor"></a>source_link_manager 

 `source_link_manager` 개체를 생성합니다.  
  
```
source_link_manager();
```  
  
##  <a name="a-namedtora-sourcelinkmanager"></a><a name="dtor"></a>~ source_link_manager 

 소멸은 `source_link_manager` 개체입니다.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [single_link_registry 클래스](single-link-registry-class.md)   
 [multi_link_registry 클래스](multi-link-registry-class.md)

