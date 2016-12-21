---
title: "array 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array 클래스"
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# array 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

액셀러레이터로 데이터 이동 하는 데 사용 하는 데이터 컨테이너를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
friend class array;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value_type`  
 데이터의 요소 형식입니다.  
  
 `_Rank`  
 배열의 차수입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[array:: array 생성자](#array__array_constructor)|`array` 클래스의 새 인스턴스를 초기화합니다.|  
|[배열:: ~ array 소멸자](#array___dtorarray_destructor)|소멸은 `array` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[array:: copy_to 메서드](#array__copy_to_method)|배열의 내용을 다른 배열에 복사 합니다.|  
|[array:: data 메서드](#array__data_method)|배열의 원시 데이터에 대 한 포인터를 반환합니다.|  
|[array:: get_accelerator_view 메서드](#array__get_accelerator_view_method)|반환 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 배열 할당 된 위치를 나타내는 개체입니다. 이 속성은 CPU에만 액세스할 수 있습니다.|  
|[array:: get_associated_accelerator_view 메서드](#array__get_associated_accelerator_view_method)|두 번째 가져옵니다 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 인스턴스화할 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 [배열](../../../parallel/amp/reference/array-class.md) 개체입니다.|  
|[array:: get_cpu_access_type 메서드](#array__get_cpu_access_type_method)|반환 된 [access_type](access_type%20Enumeration.md) 배열입니다. 이 메서드는 CPU에만 액세스할 수 있습니다.|  
|[array:: get_extent 메서드](#array__get_extent_method)|반환 된 [익스텐트](../../../parallel/amp/reference/extent-class-cpp-amp.md) 배열 개체입니다.|  
|[array:: reinterpret_as 메서드](#array__reinterpret_as_method)|에 있는 모든 요소를 포함 하는 1 차원 배열을 반환는 `array` 개체입니다.|  
|[array:: section 메서드](#array__section_method)|하위 섹션을 반환 된 [배열](../../../parallel/amp/reference/array-class.md) 지정된 된 origin 하 고, 필요에 따라 하에 있는 개체에는 지정 된 범위입니다.|  
|[array:: view_as 메서드](#array__view_as_method)|반환 된 [array_view](../../../parallel/amp/reference/array-view-class.md) 에서 생성 된 개체는 `array` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[array:: operator std:: vector&lt;value_type&gt; 연산자](#array__operator_std__vector_lt__value_type_gt__operator)|사용 하 여 `copy(*this, vector)` 변환할 암시적으로 배열 한 std::[벡터](../../../standard-library/vector-class.md) 개체입니다.|  
|[array:: operator () 연산자](#array__operator___operator)|매개 변수에 의해 지정 된 요소 값을 반환 합니다.|  
|[array:: operator] 연산자](#array__operator_at_operator)|지정된 된 인덱스에 있는 요소를 반환 합니다.|  
|[array:: operator = 연산자](#array__operator_eq_operator)|지정 된 내용을 복사 `array` 을 여기에 개체입니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[array:: rank 상수](#array__rank_constant)|배열의 차수를 저장합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[array:: accelerator_view 데이터 멤버](#array__accelerator_view_data_member)|가져옵니다는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 배열 할당 된 위치를 나타내는 개체입니다. 이 속성은 CPU에만 액세스할 수 있습니다.|  
|[array:: associated_accelerator_view 데이터 멤버](#array__associated_accelerator_view_data_member)|두 번째 가져옵니다 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 인스턴스화할 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 [배열](../../../parallel/amp/reference/array-class.md) 개체입니다.|  
|[array:: cpu_access_type 데이터 멤버](#array__cpu_access_type_data_member)|가져옵니다는 [access_type](access_type%20Enumeration.md) CPU 배열의 저장소에 액세스 하는 방법을 나타내는입니다.|  
|[array:: extent 데이터 멤버](#array__extent_data_member)|배열의 모양을 정의 하는 범위를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 형식 `array<T,N>` 조밀한 및 정규식을 나타냅니다 (부정형 있는 경우) *N*-가속기 또는 CPU와 같은 특정 위치에 있는 차원 배열입니다. 배열에 있는 요소의 데이터 형식이 `T`, 대상 가속기와 호환 되는 형식 이어야 합니다. 하지만 순위, `N`, (의 배열 정적으로 결정 됩니다 종류의 일부인, 배열의 범위는 런타임에 의해 결정 됩니다 클래스를 사용 하 여 표현 됩니다 `extent<N>`합니다.  
  
 배열 수에는 제한이 차원의 일부 기능에 맞게 있지만 `array` 순위 1, 2 및 3을 사용 하 여 개체입니다. 차원 인수를 생략 하면 기본값은 1입니다.  
  
 배열 데이터는 메모리에 연속적으로 배치 됩니다. 덜 중요 한 차원에 따라 다른 요소는 메모리 내에서 인접해입니다.  
  
 배열은 배열을 다른 배열에 복사 되 면 전체 복사본을이 이루어지기 때문에 논리적으로 값 형식으로 간주 됩니다. 두 배열이 하지는 동일한 데이터를 가리킵니다.  
  
  `array<T,N>` 형식이 여러 시나리오에 사용 됩니다.  
  
-   액셀러레이터에서의 계산에 사용할 수 있는 데이터 컨테이너입니다.  
  
-   하는 컨테이너로 데이터 (사용할 수 있는 다른 배열에서 복사를) 호스트 CPU에 대 한 메모리를 보유 합니다.  
  
-   호스트와 장치 간 복사본에 빠른 중간자 역할을 준비 개체입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `array`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namearraydtorarraydestructora-arrayarray-destructor"></a><a name="array___dtorarray_destructor"></a>  배열:: ~ array 소멸자  
 소멸은 `array` 개체입니다.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="a-namearrayacceleratorviewdatamembera-arrayacceleratorview-data-member"></a><a name="array__accelerator_view_data_member"></a>  array:: accelerator_view 데이터 멤버  
 가져옵니다는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 배열 할당 된 위치를 나타내는 개체입니다. 이 속성은 CPU에만 액세스할 수 있습니다.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="a-namearrayarrayconstructora-arrayarray-constructor"></a><a name="array__array_constructor"></a>  array:: array 생성자  
 새 인스턴스를 초기화는 [array 클래스](../../../parallel/amp/reference/array-class.md)합니다. 에 대 한 기본 생성자는 `array<T,N>`합니다. 모든 생성자만 CPU에서 실행 됩니다. Direct3D 대상에서 실행할 수는 없습니다.  
  
```  
explicit array(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
explicit array(
    int _E0) restrict(cpu);

 
explicit array(
    int _E0,  
    int _E1) restrict(cpu);

 
explicit array(
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);

 
array(
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
array(
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
explicit array(
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);

 
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);

 
array(
    const array& _Other) restrict(cpu);

 
array(
    array&& _Other) restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Associated_Av`  
 배열의 기본 대상 위치를 지정 하는 accelerator_view 합니다.  
  
 `_Av`  
  [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 배열의 위치를 지정 하는 개체입니다.  
  
 `_Cpu_access_type`  
 원하는 [access_type](access_type%20Enumeration.md)  CPU에서 배열에 대 한 합니다. 이 매개 변수는 기본값은 `access_type_auto` CPU를 그대로 두고 `access_type` 런타임에 결정 합니다. 실제 CPU `access_type` 배열을 사용 하 여 쿼리할 수에 대 한는 `get_cpu_access_type` 메서드.  
  
 `_Extent`  
 배열의 각 차원에 대 한 범위입니다.  
  
 `_E0`  
 이 섹션의 범위는 가장 중요 한 구성 요소입니다.  
  
 `_E1`  
 이 섹션의 범위는 다음 기능을-가장 중요 한 구성 요소입니다.  
  
 `_E2`  
 이 섹션의 범위는 덜 중요 한 구성 요소입니다.  
  
 `_InputIterator`  
 입력된 interator의 형식입니다.  
  
 `_Src`  
 복사할 개체입니다.  
  
 `_Src_first`  
 소스 컨테이너에는 시작 반복기입니다.  
  
 `_Src_last`  
 소스 컨테이너에 사용 되는 끝 반복기입니다.  
  
 `_Other`  
 다른 데이터 원본입니다.  
  
 `_Rank`  
 섹션의 순위입니다.  
  
 `value_type`  
 복사 된 요소의 데이터 형식입니다.  
  
##  <a name="a-namearrayassociatedacceleratorviewdatamembera-arrayassociatedacceleratorview-data-member"></a><a name="array__associated_accelerator_view_data_member"></a>  array:: associated_accelerator_view 데이터 멤버  
 두 번째 가져옵니다 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 인스턴스화할 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 [배열](../../../parallel/amp/reference/array-class.md) 개체입니다.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namearraycopytomethoda-arraycopyto-method"></a><a name="array__copy_to_method"></a>  array:: copy_to 메서드  
 내용을 복사는 [배열](../../../parallel/amp/reference/array-class.md) 다른 `array`합니다.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
  [array_view](../../../parallel/amp/reference/array-view-class.md) 복사할 개체입니다.  
  
##  <a name="a-namearraycpuaccesstypedatamembera-arraycpuaccesstype-data-member"></a><a name="array__cpu_access_type_data_member"></a>  array:: cpu_access_type 데이터 멤버  
 이 배열에 대 한 허용 CPU access_type를 가져옵니다.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="a-namearraydatamethoda-arraydata-method"></a><a name="array__data_method"></a>  array:: data 메서드  
 원시 데이터에 대 한 포인터를 반환 된 [배열](../../../parallel/amp/reference/array-class.md)합니다.  
  
```  
value_type* data() restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>반환 값  
 배열의 원시 데이터에 대 한 포인터입니다.  
  
##  <a name="a-namearrayextentdatamembera-arrayextent-data-member"></a><a name="array__extent_data_member"></a>  array:: extent 데이터 멤버  
 가져옵니다는 [익스텐트](../../../parallel/amp/reference/extent-class-cpp-amp.md) 개체의 모양을 정의 하는 [배열](../../../parallel/amp/reference/array-class.md)합니다.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearraygetacceleratorviewmethoda-arraygetacceleratorview-method"></a><a name="array__get_accelerator_view_method"></a>  array:: get_accelerator_view 메서드  
 반환 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 위치를 나타내는 개체입니다 위치는 [배열](../../../parallel/amp/reference/array-class.md) 개체가 할당 됩니다. 이 속성은 CPU에만 액세스할 수 있습니다.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>반환 값  
  `accelerator_view` 개체 위치를 나타내는 위치는 [배열](../../../parallel/amp/reference/array-class.md) 개체가 할당 됩니다.  
  
##  <a name="a-namearraygetassociatedacceleratorviewmethoda-arraygetassociatedacceleratorview-method"></a><a name="array__get_associated_accelerator_view_method"></a>  array:: get_associated_accelerator_view 메서드  
 두 번째 가져옵니다 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 인스턴스화할 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 [배열](../../../parallel/amp/reference/array-class.md) 개체입니다.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>반환 값  
 두 번째 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 스테이징 생성자에 전달 된 개체입니다.  
  
##  <a name="a-namearraygetcpuaccesstypemethoda-arraygetcpuaccesstype-method"></a><a name="array__get_cpu_access_type_method"></a>  array:: get_cpu_access_type 메서드  
 이 배열에 대 한 허용 되는 CPU access_type를 반환 합니다.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-namearraygetextentmethoda-arraygetextent-method"></a><a name="array__get_extent_method"></a>  array:: get_extent 메서드  
 반환 된 [익스텐트](../../../parallel/amp/reference/extent-class-cpp-amp.md) 의 개체는 [배열](../../../parallel/amp/reference/array-class.md)합니다.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>반환 값  
  `extent` 의 개체는 [배열](../../../parallel/amp/reference/array-class.md)합니다.  
  
##  <a name="a-namearrayoperatorstdvectorltvaluetypegtoperatora-arrayoperator-stdvectorltvaluetypegt-operator"></a><a name="array__operator_std__vector_lt__value_type_gt__operator"></a>  array:: operator std:: vector&lt;value_type&gt; 연산자  
 사용 하 여 `copy(*this, vector)` 배열 std:: vector 개체를 암시적으로 변환할 합니다.  
  
' ' 연산자 std:: vector \< value_type > () const restrict(cpu);
```  
  
### Parameters  
 `value_type`  
 The data type of the elements of the vector.  
  
### Return Value  
 An object of type `vector<T>` that contains a copy of the data that is contained in the array.  
  
##  <a name="array__operator___operator"></a>  array::operator() Operator  
 Returns the element value that is specified by the parameters.  
  
```  
value_type & operator () (const 인덱스 \< _Rank > & _Index) restrict(amp,cpu);

 
const value_type 및 operator () (const 인덱스 \< _Rank > & _Index) const restrict(amp,cpu);

 
value_type & restrict(amp,cpu) (_I0 int, int _I1) operator ();

 
const value_type 및 operator () (_I0 int, int _I1) const restrict(amp,cpu);

 
value_type & restrict(amp,cpu) (int _I0, _I1 int, int _I2) operator ();

 
const value_type 및 operator () (int _I0, _I1 int, int _I2) const restrict(amp,cpu);

 
typename details::_Projection_result_type \< value_type, _Rank >:: operator () (int (_i)) restrict(amp,cpu) _Result_type;

 
typename details::_Projection_result_type \< value_type, _Rank >:: operator () (int (_i)) const restrict(amp,cpu) _Const_result_type;
```  
  
### Parameters  
 `_Index`  
 The location of the element.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_I`  
 The location of the element.  
  
### Return Value  
 The element value specified by the parameters.  
  
##  <a name="array__operator_at_operator"></a>  array::operator[] Operator  
 Returns the element that is at the specified index.  
  
```  
value_type & 연산자 (const 인덱스 \< _Rank > & _Index) restrict(amp,cpu);

 
const value_type & 연산자 (const 인덱스 \< _Rank > & _Index) const restrict(amp,cpu);

 
typename details::_Projection_result_type \< value_type, _Rank >:: _Result_type 연산자[](int _I) restrict(amp,cpu);

 
typename details::_Projection_result_type \< value_type, _Rank >:: _Const_result_type 연산자[](int _I) const restrict(amp,cpu);
```  
  
### Parameters  
 `_Index`  
 The index.  
  
 `_I`  
 The index.  
  
### Return Value  
 The element that is at the specified index.  
  
##  <a name="array__operator_eq_operator"></a>  array::operator= Operator  
 Copies the contents of the specified [array](../../../parallel/amp/reference/array-class.md) object.  
  
```  
배열 & 연산자 (const 배열 & _Other) = restrict(cpu);

 
배열 & 연산자 = (배열 & & _Other) restrict(cpu);

 
배열 & 연산자 = (const array_view \< const value_type, _Rank > & _Src) restrict(cpu);
```  
  
### Parameters  
 `_Other`  
 The `array` object to copy from.  
  
 `_Src`  
 The `array` object to copy from.  
  
### Return Value  
 A reference to this `array` object.  
  
##  <a name="array__rank_constant"></a>  array::rank Constant  
 Stores the rank of the [array](../../../parallel/amp/reference/array-class.md).  
  
```  
static const int 순위 = _Rank;  
```  
  
##  <a name="array__section_method"></a>  array::section Method  
 Returns a subsection of the [array](../../../parallel/amp/reference/array-class.md) object that is at the specified origin and, optionally, that has the specified extent.  
  
```  
array_view \< value_type, _Rank > (const Concurrency::index \< _Rank > & _Section_origin, 섹션  
    const Concurrency::extent \< _Rank > & _Section_extent) restrict(amp,cpu);

 
array_view \< const value_type, _Rank > (const Concurrency::index \< _Rank > & _Section_origin, 섹션  
    const Concurrency::extent \< _Rank > & _Section_extent) const restrict(amp,cpu);

 
array_view \< value_type, _Rank > (const Concurrency::extent \< _Rank > & _Ext) 섹션 restrict(amp,cpu);

 
array_view \< const value_type, _Rank > (const Concurrency::extent \< _Rank > & _Ext) 섹션 const restrict(amp,cpu);

 
array_view \< value_type, _Rank > (const 인덱스 \< _Rank > & _Idx) 섹션 restrict(amp,cpu);

 
array_view \< const value_type, _Rank > (const 인덱스 \< _Rank > & _Idx) 섹션 const restrict(amp,cpu);

 
array_view \< value_type 1 > 섹션 (int _I0,  
    int _E0) restrict(amp,cpu);

 
array_view \< const value_type, 1 > 섹션 (int _I0,  
    int _E0) const restrict(amp,cpu);

 
array_view \< value_type, 2 > 섹션 (int _I0,  
    int _I1  
    int _E0  
    int _E1) restrict(amp,cpu);

 
array_view \< const value_type, 2 > 섹션 (int _I0,  
    int _I1  
    int _E0  
    int _E1) const restrict(amp,cpu);

 
array_view \< value_type 3 > 섹션 (int _I0,  
    int _I1  
    int _I2  
    int _E0  
    int _E1  
    int _E2) restrict(amp,cpu);

 
array_view \< const value_type, 3 > 섹션 (int _I0,  
    int _I1  
    int _I2  
    int _E0  
    int _E1  
    int _E2) const restrict(amp,cpu);
```  
  
### Parameters  
 `_E0`  
 The most significant component of the extent of this section.  
  
 `_E1`  
 The next-to-most-significant component of the extent of this section.  
  
 `_E2`  
 The least significant component of the extent of this section.  
  
 `_Ext`  
 The [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) object that specifies the extent of the section. The origin is 0.  
  
 `_Idx`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin. The subsection is the rest of the extent.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_Rank`  
 The rank of the section.  
  
 `_Section_extent`  
 The [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) object that specifies the extent of the section.  
  
 `_Section_origin`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin.  
  
 `value_type`  
 The data type of the elements that are copied.  
  
### Return Value  
 Returns a subsection of the `array` object that is at the specified origin and, optionally, that has the specified extent. When only the `index` object is specified, the subsection contains all elements in the associated grid that have indexes that are larger than the indexes of the elements in the `index` object.  
  
##  <a name="array__view_as_method"></a>  array::view_as Method  
 Reinterprets this array as an [array_view](../../../parallel/amp/reference/array-view-class.md) of a different rank.  
  
```  
서식 파일 \< int _New_rank  
>  
array_view \< value_type, _New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) restrict(amp,cpu);

 
서식 파일 \< int _New_rank  
>  
array_view \< const value_type, _New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) const restrict(amp,cpu);
```  
  
### Parameters  
 `_New_rank`  
 The rank of the `extent` object passed as a parameter.  
  
 `_View_extent`  
 The extent that is used to construct the new [array_view](../../../parallel/amp/reference/array-view-class.md) object.  
  
 `value_type`  
 The data type of the elements in both the original [array](../../../parallel/amp/reference/array-class.md) object and the returned `array_view` object.  
  
### Return Value  
 The [array_view](../../../parallel/amp/reference/array-view-class.md) object that is constructed.  
  
## See Also  
 [Concurrency Namespace (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
