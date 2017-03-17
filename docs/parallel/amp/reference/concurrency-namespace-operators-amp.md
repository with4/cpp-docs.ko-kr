---
title: "동시성 네임 스페이스 연산자 (AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: 
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: 676f3e836082dc3286a45f8d59db83c969964058
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators-amp"></a>동시성 네임 스페이스 연산자 (AMP)
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator*](#operator_star)|  
|[operator+](#operator_add)|[operator-](#operator-)|[operator/](#operator_div)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a>  operator==   
 지정된 된 인수 같은지 여부를 결정 합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 비교할 튜플 중 하나입니다.  
  
 `_Rhs`  
 비교할 튜플 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`튜플을 동일 하면 그렇지 않으면 `false`합니다.  
  
##  <a name="operator_neq"></a>  operator!=   
 지정된 된 인수가 같은지 여부를 결정 합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 비교할 튜플 중 하나입니다.  
  
 `_Rhs`  
 비교할 튜플 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`튜플을 같지 않으면; 그렇지 않으면 `false`합니다.  
  
##  <a name="operator_add"></a>  operator+   

 지정된 된 인수의 component-wise 합을 계산 합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 추가할 인수 중 하나입니다.  
  
 `_Rhs`  
 추가할 인수 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인수의 component-wise 합입니다.  
  
##  <a name="operator-"></a>  operator-   

 지정된 된 인수 간의 component-wise 차이 계산 합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 인수에서 뺄입니다.  
  
 `_Rhs`  
 뺄 인수입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인수 간의 component-wise 차이입니다.  
  
##  <a name="operator_star"></a>  operator*   

 지정 된 인수가 component-wise 곱을 계산 합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 곱할 튜플 중 하나입니다.  
  
 `_Rhs`  
 곱할 튜플 중 하나입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인수의 component-wise 곱입니다.  
  

##  <a name="operator_div"></a>  operator/   
 지정된 된 인수 component-wise 몫을 계산합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 나눌 튜플입니다.  
  
 `_Rhs`  
 으로 나누려고 튜플입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인수의 component-wise 몫입니다.  
  
##  <a name="operator_mod"></a>  operator%   

 두 번째는 지정 된 인수에 의해 지정된 된 첫 번째 인수의 모듈러스를 계산합니다.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rank`  
 튜플 인수의 순위입니다.  
  
 `_Lhs`  
 있는 튜플은 모듈로 계산 됩니다.  
  
 `_Rhs`  
 튜플을 모듈로 여 합니다.  
  
### <a name="return-value"></a>반환 값  
 결과 첫 번째 지정 된 인수 모듈러스 지정된 된 두 번째 인수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace](concurrency-namespace-cpp-amp.md)

