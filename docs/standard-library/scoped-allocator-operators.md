---
title: "&lt;scoped_allocator&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs:
- C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 2b4a7cd767385fd0eb3b7bfb0c98cd6bd3a411e6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt; 연산자
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 두 `scoped_allocator_adaptor` 개체가 다른지 비교합니다.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 왼쪽 `scoped_allocator_adaptor` 개체입니다.  
  
 `right`  
 오른쪽 `scoped_allocator_adaptor` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `!(left == right)`  
  
##  <a name="op_eq_eq"></a>  operator==  
 두 `scoped_allocator_adaptor` 개체가 같은지 테스트합니다.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 왼쪽 `scoped_allocator_adaptor` 개체입니다.  
  
 `right`  
 오른쪽 `scoped_allocator_adaptor` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`  
  
## <a name="see-also"></a>참고 항목  
 [<scoped_allocator>](../standard-library/scoped-allocator.md)

