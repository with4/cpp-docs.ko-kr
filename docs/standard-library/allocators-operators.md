---
title: "&lt;allocators&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6185bc74c530d6327d0ac37a5425a7653ba36841
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 연산자
|||  
|-|-|  
|[operator!=](#operator_neq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  operator!=  
 지정된 클래스의 할당자 개체가 다른지 테스트합니다.  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|같지 않은지를 테스트할 할당자 개체 중 하나입니다.|  
|`right`|같지 않은지를 테스트할 할당자 개체 중 하나입니다.|  
  
### <a name="return-value"></a>반환 값  
 할당자 개체가 같지 않으면 **true**이고 할당자 개체가 같으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 연산자가 `!(left == right)`를 반환합니다.  
  
##  <a name="operator_eq_eq"></a>  operator==  
 지정된 클래스의 할당자 개체가 같은지 테스트합니다.  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|같은지를 테스트할 할당자 개체 중 하나입니다.|  
|`right`|같은지를 테스트할 할당자 개체 중 하나입니다.|  
  
### <a name="return-value"></a>반환 값  
 할당자 개체가 같으면 **true**이고 할당자 개체가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 연산자가 `left.equals(right)`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




