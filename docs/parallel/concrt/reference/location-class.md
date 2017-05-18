---
title: "위치 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
dev_langs:
- C++
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
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
ms.openlocfilehash: a0b64804ebfea3ad2c172c509aeffd485f4fe30a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="location-class"></a>위치 클래스
하드웨어의 실제 위치에 대한 추상화입니다.  
  
## <a name="syntax"></a>구문  
  
```
class location;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[위치](#ctor)|오버로드됨. `location` 개체를 생성합니다.|  
|[~ location 소멸자](#dtor)|`location` 개체를 제거합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[현재](#current)|호출 스레드가 실행 중인 가장 구체적인 장소를 나타내는 `location` 개체를 반환합니다.|  
|[from_numa_node](#from_numa_node)|지정된 NUMA 노드를 나타내는 `location` 개체를 반환합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator!=](#operator_neq)|두 `location` 개체가 서로 다른 위치를 나타내는지 여부를 확인합니다.|  
|[operator=](#operator_eq)|다른 `location` 개체의 내용을 여기에 할당합니다.|  
|[operator==](#operator_eq_eq)|두 결정 `location` 개체는 같은 위치를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `location`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a>~ 위치 

 `location` 개체를 제거합니다.  
  
```
~location();
```  
  
##  <a name="current"></a>현재 

 호출 스레드가 실행 중인 가장 구체적인 장소를 나타내는 `location` 개체를 반환합니다.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>반환 값  
 호출 스레드가 실행 중인 가장 구체적인 장소를 나타내는 위치입니다.  
  
##  <a name="from_numa_node"></a>from_numa_node 

 지정된 NUMA 노드를 나타내는 `location` 개체를 반환합니다.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>매개 변수  
 `_NumaNodeNumber`  
 위치를 생성하기 위한 NUMA 노드 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 `_NumaNodeNumber` 매개 변수로 지정된 NUMA 노드를 나타내는 위치입니다.  
  
##  <a name="ctor"></a>위치 

 `location` 개체를 생성합니다.  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>주의  
 기본적으로 생성되는 위치는 시스템 전체를 나타냅니다.  
  
##  <a name="operator_neq"></a>연산자! = 

 두 `location` 개체가 서로 다른 위치를 나타내는지 여부를 확인합니다.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
  
### <a name="return-value"></a>반환 값  
 두 위치가 다르면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="operator_eq"></a>연산자 = 

 다른 `location` 개체의 내용을 여기에 할당합니다.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
 소스 `location` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq_eq"></a>연산자 = = 

 두 결정 `location` 개체는 같은 위치를 나타냅니다.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rhs`  
  
### <a name="return-value"></a>반환 값  
 `true`두 위치가 동일 하면 및 `false` 그렇지 않은 경우.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)

