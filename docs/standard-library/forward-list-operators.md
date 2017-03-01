---
title: "&lt;forward_list&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a560de0a7587b5552fc663bdd2b44734a66b5f73
ms.lasthandoff: 02/24/2017

---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체와 같은지 테스트합니다.  
  
```
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `operator==`을 오버로드하여 템플릿 클래스 `forward_list`의 개체 두 개를 비교합니다. 함수에서 `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`을 반환합니다.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체와 같지 않은지 테스트합니다.  
  
```
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 목록이 같지 않으면 **true**이고 목록이 같으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `!(left == right)`를 반환합니다.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 작은지 테스트합니다.  
  
```
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 목록이 연산자 우변의 목록보다 작으며 같지 않으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `operator<`을 오버로드하여 템플릿 클래스 `forward_list`의 개체 두 개를 비교합니다. 함수에서 `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`을 반환합니다.  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 작거나 같은지 테스트합니다.  
  
```
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 목록이 연산자 우변의 목록보다 작거나 같으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `!(right < left)`를 반환합니다.  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 큰지 테스트합니다.  
  
```
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 목록이 연산자 우변의 목록보다 크면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `right < left`를 반환합니다.  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 크거나 같은지 테스트합니다.  
  
```
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 목록이 연산자 우변의 목록보다 크거나 같으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수가 `!(left < right)`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [<forward_list>](../standard-library/forward-list.md)




