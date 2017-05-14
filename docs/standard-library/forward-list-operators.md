---
title: "&lt;forward_list&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: ddf548e760d723bff19b58ac8dfe6ec60acdbbcc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  operator==  
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
  
##  <a name="op_neq"></a>  operator!=  
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
  
##  <a name="op_lt"></a>  operator&lt;  
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
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
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
  
##  <a name="op_gt"></a>  operator&gt;  
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
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
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




