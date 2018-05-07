---
title: Platform::Collections::VectorIterator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deaab183a092a073c6681004654312485959e924
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator 클래스
Windows 런타임 IVector 인터페이스에서 파생 된 개체에 대 한 표준 템플릿 라이브러리 반복기를 제공 합니다.  
  
 VectorIterator는 VectorProxy 형식의 요소를 저장 하는 프록시 반복기\<T >. 그러나 프록시 개체는 사용자 코드에 거의 표시되지 않습니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
template <typename T>  
class VectorIterator;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 VectorIterator 템플릿 클래스의 형식 이름입니다.  
  
### <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`difference_type`|포인터 차이(ptrdiff_t)입니다.|  
|`iterator_category`|임의 액세스 반복기의 범주입니다(::std::random_access_iterator_tag).|  
|`pointer`|Platform::Collections::Details::VectorProxy 내부 형식에 대 한 포인터\<T > 즉, VectorIterator의 구현에 필요 합니다.|  
|`reference`|Platform::Collections::Details::VectorProxy 내부 형식에 대 한 참조\<T >, 즉, VectorIterator의 구현에 필요 합니다.|  
|`value_type`|`T` 형식 이름입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[VectorIterator::VectorIterator](#ctor)|VectorIterator 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[VectorIterator::operator- 연산자](#operator-minus)|현재 반복기에서 지정된 요소 수를 빼서 새 반복기를 계산하거나 현재 반복기에서 지정된 반복기를 빼서 반복기 간 요소 수 차이를 계산합니다.|  
|[VectorIterator::operator-- 연산자](#operator-decrement)|현재 VectorIterator를 감소시킵니다.|  
|[VectorIterator::operator!= 연산자](#operator-inequality)|현재 VectorIterator가 지정된 VectorIterator와 같지 않은지 여부를 나타냅니다.|  
|[VectorIterator::operator* 연산자](#operator-dereference)|현재 VectorIterator가 지정하는 요소에 대한 참조를 검색합니다.|  
|[VectorIterator::operator\[\]](#operator-at)|현재 VectorIterator에서 지정된 치환에 해당하는 요소에 대한 참조를 검색합니다.|  
|[VectorIterator::operator+ 연산자](#operator-plus)|지정된 VectorIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorIterator를 반환합니다.|  
|[VectorIterator::operator++ 연산자](#operator-increment)|현재 VectorIterator를 증가시킵니다.|  
|[VectorIterator::operator+= 연산자](#operator-plus-assign)|지정된 치환으로 현재 VectorIterator를 늘립니다.|  
|[VectorIterator::operator< 연산자](#operator-less-than)|현재 VectorIterator가 지정된 VectorIterator보다 작은지 여부를 나타냅니다.|  
|[Vectoriterator::\<= 연산자](#operator-less-than-or-equals)|현재 VectorIterator가 지정된 VectorIterator보다 작거나 같은지 여부를 나타냅니다.|  
|[VectorIterator::operator-= 연산자](#operator-subtract-assign)|지정된 치환으로 현재 VectorIterator를 줄입니다.|  
|[VectorIterator::operator== 연산자](#operator-equality)|현재 VectorIterator가 지정된 VectorIterator와 같은지 여부를 나타냅니다.|  
|[VectorIterator::operator> 연산자](#operator-greater-than)|현재 VectorIterator가 지정된 VectorIterator보다 큰지 여부를 나타냅니다.|  
|[VectorIterator::operator-> 연산자](#operator-arrow)|현재 VectorIterator가 참조하는 요소의 주소를 검색합니다.|  
|[VectorIterator::operator>= 연산자](#operator-greater-than-or-equal)|현재 VectorIterator가 지정된 VectorIterator보다 크거나 같은지 여부를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `VectorIterator`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  

## <a name="operator-arrow"></a>  VectorIterator::operator-&gt; Operator
현재 VectorIterator가 참조하는 요소의 주소를 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 VectorIterator가 참조하는 요소의 값입니다.  
  
 반환 값의 형식은 이 연산자의 구현에 필요한 지정되지 않은 내부 형식입니다.  
  


## <a name="operator-decrement"></a>  VectorIterator::operator-- Operator
현재 VectorIterator를 감소시킵니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(int);  
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 구문은 현재 VectorIterator를 감소시킨 다음 반환합니다. 두 번째 구문은 현재 VectorIterator의 복사본을 반환한 다음 현재 VectorIterator를 감소시킵니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 VectorIterator 구문은 현재 VectorIterator를 사전에 감소시킵니다.  
  
 두 번째 구문은 현재 VectorIterator를 사후에 감소시킵니다. `int` 두 번째 구문의 형식은 실제 정수 피연산자가 아니라 후 위 감소 작업을 나타냅니다.  
  


## <a name="operator-dereference"></a>  Vectoriterator:: 연산자
현재 VectorIterator가 지정하는 요소의 주소를 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 VectorIterator가 지정하는 요소입니다.  
  


## <a name="operator-equality"></a>  Vectoriterator:: Operator = = 연산자
현재 VectorIterator가 지정된 VectorIterator와 같은지 여부를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool operator==(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 VectorIterator가 `true`와 같지 않으면 `other`이고, 같으면 `false`입니다.  
  


## <a name="operator-greater-than"></a>  Vectoriterator::&gt; 연산자
현재 VectorIterator가 지정된 VectorIterator보다 큰지 여부를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
bool operator>(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 현재 VectorIterator 보다 큰 경우 `other`, 그렇지 않으면 `false`합니다.  
  


## <a name="operator-greater-than-or-equals"></a>  Vectoriterator::&gt;= 연산자
현재 VectorIterator가 지정된 VectorIterator보다 크거나 같은지 여부를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
bool operator>=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 VectorIterator가 `true`보다 크거나 같으면 `other`이고, 그렇지 않으면 `false`입니다.    


## <a name="operator-increment"></a>  Vectoriterator:: Operator + + 연산자
현재 VectorIterator를 증가시킵니다.  
  
### <a name="syntax"></a>구문  
  
```    
VectorIterator& operator++();  
VectorIterator operator++(int);  
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 구문은 현재 VectorIterator를 증가시킨 다음 반환합니다. 두 번째 구문은 현재 VectorIterator의 복사본을 반환한 다음 현재 VectorIterator를 증가시킵니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 VectorIterator 구문은 현재 VectorIterator를 사전에 증가시킵니다.  
  
 두 번째 구문은 현재 VectorIterator를 사후에 증가시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 증가 연산을 나타냅니다.  
  


## <a name="operator-inequality"></a>  Vectoriterator:: Operator! = 연산자
현재 VectorIterator가 지정된 VectorIterator와 같지 않은지 여부를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool operator!=(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 현재 VectorIterator와 같지 않으면 `other`, 그렇지 않으면 `false`합니다.  
  


## <a name="operator-less-than"></a>  Vectoriterator::&lt; 연산자
현재 VectorIterator가 지정된 VectorIterator보다 작은지 여부를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
bool operator<(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 VectorIterator가 `true`보다 작으면 `other`이고, 크거나 같으면 `false`입니다.  
  


## <a name="operator-less-than-or-equals"></a>  Vectoriterator::&lt;= 연산자
현재 VectorIterator가 지정된 VectorIterator보다 작거나 같은지 여부를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
bool operator<=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 현재 VectorIterator가 보다 작거나 같은 경우 `other`, 그렇지 않으면 `false`합니다.  
  


## <a name="operator-minus"></a>  Vectoriterator:: Operator-연산자
현재 반복기에서 지정된 요소 수를 빼서 새 반복기를 계산하거나 현재 반복기에서 지정된 반복기를 빼서 반복기 간 요소 수 차이를 계산합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
VectorIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `n`  
 요소 수입니다.  
  
 `other`  
 다른 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 연산자 구문은 VectorIterator 개체를 반환 `n` 현재 VectorIterator 보다 작은 요소입니다. 두 번째 연산자 구문은 현재 사이의 요소 수를 반환 및 `other` VectorIterator입니다.  
  


## <a name="operator-plus-assign"></a>  Vectoriterator:: Operator + = 연산자
지정된 치환으로 현재 VectorIterator를 늘립니다.  
  
### <a name="syntax"></a>구문  
  
```  
VectorIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>매개 변수  
 `n`  
 정수 치환입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트된 VectorIterator입니다.  
  


## <a name="operator-plus"></a>  ectorIterator::operator + 연산자
지정된 VectorIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorIterator를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
VectorIterator operator+(difference_type n);  
  
template <typename T>  
inline VectorIterator<T> operator+(
  ptrdiff_t n, 
  const VectorIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 두 번째 구문에서 VectorIterator의 형식 이름입니다.  
  
 `n`  
 정수 치환입니다.  
  
 `i`  
 두 번째 구문의 VectorIterator입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 구문에서 현재 VectorIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorIterator입니다.  
  
 두 번째 구문에서 매개 변수 `i` 시작 부분의 지정된 치환에 해당하는 요소를 참조하는 VectorIterator입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 구문 예제  
  


## <a name="operator-minus-equals"></a>  Vectoriterator:: Operator-= 연산자
지정된 치환으로 현재 VectorIterator를 줄입니다.  
  
### <a name="syntax"></a>구문  
  
```  
VectorIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>매개 변수  
 `n`  
 정수 치환입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트된 VectorIterator입니다.  
  


## <a name="operator-at"></a>  VectorIterator::operator\[\]
현재 VectorIterator에서 지정된 치환에 해당하는 요소에 대한 참조를 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```    
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `n`  
 정수 치환입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 VectorIterator에서 `n` 요소에 의해 치환되는 요소입니다.  
  


## <a name="ctor"></a>  Vectoriterator:: Vectoriterator 생성자
VectorIterator 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```    
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
### <a name="parameters"></a>매개 변수  
 `v`  
 IVector\<T > 개체입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 구문 예제에서는 기본 생성자를 호출합니다. 두 번째 구문 예제는 IVector에서 VectorIterator를 만드는 사용 되는 명시적 생성자\<T > 개체입니다.  
  


  
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)