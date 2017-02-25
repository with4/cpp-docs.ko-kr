---
title: "array_view 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::array_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array_view 클래스"
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# array_view 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

다른 컨테이너에 저장 된 데이터에 대 한 N 차원 보기를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <
    typename value_type,  
    int _Rank = 1  
>  
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
 
template <
    typename value_type,  
    int _Rank  
>  
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value_type`  
 데이터 형식의 요소에는 `array_view` 개체입니다.  
  
 `_Rank`  
 순위는 `array_view` 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[array_view:: array_view 생성자](#array_view__array_view_constructor)|`array_view` 클래스의 새 인스턴스를 초기화합니다. 에 대 한 기본 생성자는 `array<T,N>`합니다. 모든 생성자만 CPU에서 실행 되도록 제한 되며 Direct3D 대상에서 실행할 수 없습니다.|  
|[array_view:: ~ array_view 소멸자](#array_view___dtorarray_view_destructor)|소멸은 `array_view` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[array_view:: copy_to 메서드](#array_view__copy_to_method)|내용을 복사는 `array_view` 를 호출 하 여 지정한 대상 개체 `copy(*this, dest)`합니다.|  
|[array_view:: data 메서드](#array_view__data_method)|원시 데이터에 대 한 포인터를 반환 된 `array_view`합니다.|  
|[array_view:: discard_data 메서드](#array_view__discard_data_method)|이 보기는 현재 데이터를 삭제 합니다.|  
|[array_view:: get_extent 메서드](#array_view__get_extent_method)|Array_view 개체의 범위 개체를 반환합니다.|  
|[array_view:: get_ref 메서드](#array_view__get_ref_method)|인덱싱된 요소에 대 한 참조를 반환합니다.|  
|[array_view:: get_source_accelerator_view 메서드](#array_view__get_source_accelerator_view_method)|반환 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 여기서의 데이터 소스는 `array_view` 있는 합니다.|  
|[array_view:: refresh 메서드](#array_view__refresh_method)|알립니다는 `array_view` 외부에서 수정 되었으며 바인딩된 메모리 개체는 `array_view` 인터페이스입니다. 이 메서드를 호출 오래 된 모든 캐시 된 정보를 렌더링합니다.|  
|[array_view:: reinterpret_as 메서드](#array_view__reinterpret_as_method)|에 있는 모든 요소를 포함 하는 1 차원 배열을 반환는 `array_view` 개체입니다.|  
|[array_view:: section 메서드](#array_view__section_method)|하위 섹션을 반환 된 `array_view` 지정된 된 origin 하 고, 필요에 따라 하에 있는 개체에는 지정 된 범위입니다.|  
|[array_view:: synchronize 메서드](#array_view__synchronize_method)|모든 수정 내용이 동기화는 `array_view` 해당 원본 데이터에 다시 개체입니다.|  
|[array_view:: synchronize_async 메서드](#array_view__synchronize_async_method)|모든 수정 내용이 비동기적으로 동기화는 [array_view](../../../parallel/amp/reference/array-view-class.md) 해당 원본 데이터에 다시 개체입니다.|  
|[array_view:: synchronize_to 메서드](#array_view__synchronize_to_method)|모든 수정 내용이 동기화는 `array_view` 개체는 지정 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md)합니다.|  
|[array_view:: synchronize_to_async 메서드](#array_view__synchronize_to_async_method)|모든 수정 내용이 비동기적으로 동기화는 `array_view` 개체는 지정 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md)합니다.|  
|[array_view:: view_as 메서드](#array_view__view_as_method)|생성 된 `array_view` 이 사용 하 여 다른 차수의 개체 `array_view` 개체의 데이터입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[array_view::operator() 연산자](#array_view__operator___operator)|매개 변수 또는 매개 변수에서 지정한 요소의 값을 반환 합니다.|  
|[array_view:: operator] 연산자](#array_view__operator_at_operator)|매개 변수에 의해 지정 된 요소를 반환 합니다.|  
|[array_view:: operator = 연산자](#array_view__operator_eq_operator)|지정 된 내용을 복사 `array_view` 을 여기에 개체입니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[array_view:: rank 상수](#array_view__rank_constant)|차수를 저장 된 `array_view` 개체입니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[array_view:: extent 데이터 멤버](#array_view__extent_data_member)|`extent` 개체의 모양을 정의하는 `array_view` 개체를 가져옵니다.|  
|[array_view:: source_accelerator_view 데이터 멤버](#array_view__source_accelerator_view_data_member)|가져옵니다는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 여기서의 데이터 소스는 `array_view` 있는|  
|[array_view:: value_type 데이터 멤버](#array_view__value_type_data_member)|값 형식으로는 `array_view` 및 바인딩된 배열입니다.|  
  
## <a name="remarks"></a>설명  
  `array_view` 클래스에 포함 된 데이터에 대 한 뷰를 나타냅니다.는 [배열](../../../parallel/amp/reference/array-class.md) 개체 또는의 하위 섹션은 `array` 개체입니다.  
  
 액세스할 수는 `array_view` 개체에서 원본 데이터는 로컬로 위치 또는 서로 다른 액셀러레이터 또는 일관성이 도메인에서 원격으로 합니다. 개체를 원격으로 액세스 하는 경우 뷰는 복사 하 고 필요에 따라 캐시 됩니다. 자동 캐싱의 효과 제외 하 고 `array_view` 개체와 비슷한 성능 프로필이 있는 `array` 개체입니다. 뷰를 통해 데이터에 액세스할 때 약간의 성능 저하는 합니다.  
  
 세 가지 원격 사용 시나리오가 있습니다.  
  
-   뷰는 시스템 메모리 포인터를 통해 전달 되는 [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each) 액셀러레이터를 호출 하 고 액셀러레이터 키에 액세스 합니다.  
  
-   액셀러레이터 키에 있는 배열에 보기 방법으로 전달 되는 `parallel_for_each` 다른 엑셀 러 레이 터를 호출 하 고 있는 액세스할 수 있습니다.  
  
-   Cpu 액셀러레이터에 있는 배열에 보기 액세스 합니다.  
  
 이러한 시나리오 중 하나를 참조 된 뷰가 원격 위치는 런타임에 의해 복사 되 고에 대 한 호출에 의해 수정 하는 경우는 `array_view` 개체, 로컬 위치에 다시 복사 됩니다. 런타임 변경 내용을 다시 복사 프로세스를 최적화할 수만 변경 된 요소를 복사할 수 있습니다, 또는 변경 되지 않은 부분을 복사 될 수 있습니다. 겹치는 `array_view` 원격 위치에서 참조 무결성을 유지 하기 위해 한 데이터 원본 개체를 보장 되지 않습니다.  
  
 동일한 데이터 원본에 대 한 다중 스레드 액세스를 동기화 해야 합니다.  
  
 런타임은 다음을 보장의 데이터를 캐시에 대 한 `array_view` 개체:  
  
-   에 대 한 모든 잘 동기화 된 액세스는 `array` 개체 및 `array_view` 직렬을 준수 하는 프로그램 순서에서 개체에 발생 하는-관계 하기 전에.  
  
-   겹치는 모든 잘 동기화 된 액세스 `array_view` 개체는 단일에서 동일한 엑셀 러 레이 터에 `array` 개체를 통해 별칭으로 지정 되어는 `array` 개체입니다. 합계를 유도 발생-프로그램 순서를 따르는 관계 전에 합니다. 캐시가 없습니다. 하는 경우는 `array_view` 다른 가속기에서 실행 하는 개체, 액세스의 순서 정의 경합 조건이 생성 되지 않습니다.  
  
 만들 때 한 `array_view` 시스템 메모리에 대 한 포인터를 사용 하 여 뷰를 변경 해야 `array_view` 통해서만 개체는 `array_view` 포인터입니다. 호출 해야 또는 `refresh()` 중 하나에 `array_view` 통해 대신 기본 원시 메모리를 직접 변경 되 면 시스템 포인터에 연결 된 개체의는 `array_view` 개체입니다.  
  
 두 동작은 모두에 게 알리는 `array_view` 원본 네이티브 메모리 변경 되 고 액셀러레이터 키에 있는 모든 복사본 있으며 오래 된 개체입니다. 다음이 지침을 따르는 포인터 기반 뷰 데이터 병렬 배열의 보기에 제공 된 것 같습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namearrayviewdtorarrayviewdestructora-arrayviewarrayview-destructor"></a><a name="array_view___dtorarray_view_destructor"></a>  array_view:: ~ array_view 소멸자  
 소멸은 [array_view](../../../parallel/amp/reference/array-view-class.md) 개체입니다.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="a-namearrayviewarrayviewconstructora-arrayviewarrayview-constructor"></a><a name="array_view__array_view_constructor"></a>  array_view:: array_view 생성자  
 새 인스턴스를 초기화는 [array_view](../../../parallel/amp/reference/array-view-class.md) 클래스입니다.  
  
```  
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view& _Other)restrict(amp,cpu);

 
explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    _Container& _Src) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _Container& _Src);

 
explicit array_view(
    int _E0,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const _Container& _Src) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    const _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const _Container& _Src);

 
array_view(
    int _E0,  
    const value_type* _Src)restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    const value_type* _Src) restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const value_type* _Src) restrict(amp,cpu);

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Arr_type`  
 요소 형식 데이터를 제공 하는 C 스타일 배열입니다.  
  
 `_Container`  
 지 원하는 선형 컨테이너를 지정 해야 하는 템플릿 인수 `data()` 및 `size()` 멤버입니다.  
  
 `_E0`  
 이 섹션의 범위는 가장 중요 한 구성 요소입니다.  
  
 `_E1`  
 이 섹션의 범위는 다음 기능을-가장 중요 한 구성 요소입니다.  
  
 `_E2`  
 이 섹션의 범위는 덜 중요 한 구성 요소입니다.  
  
 `_Extent`  
 이 작업의 각 차원에 있는 익스텐트의 `array_view`합니다.  
  
 `_Other`  
 형식의 개체 `array_view<T,N>` 를 초기화할 새 `array_view`합니다.  
  
 `_Size`  
 데이터를 제공 하는 C 스타일 배열의 크기입니다.  
  
 `_Src`  
 새 배열에 복사 될 원본 데이터에 대 한 포인터입니다.  
  
##  <a name="a-namearrayviewcopytomethoda-arrayviewcopyto-method"></a><a name="array_view__copy_to_method"></a>  array_view:: copy_to 메서드  
 내용을 복사는 [array_view](../../../parallel/amp/reference/array-view-class.md) 개체를 호출 하 여 지정 된 대상 개체에 `copy(*this, dest)`합니다.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 복사할 개체입니다.  
  
##  <a name="a-namearrayviewdatamethoda-arrayviewdata-method"></a><a name="array_view__data_method"></a>  array_view:: data 메서드  
 원시 데이터에 대 한 포인터를 반환 된 [array_view](../../../parallel/amp/reference/array-view-class.md)합니다.  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>반환 값  
 `array_view`의 원시 데이터에 대한 포인터입니다.  
  
##  <a name="a-namearrayviewdiscarddatamethoda-arrayviewdiscarddata-method"></a><a name="array_view__discard_data_method"></a>  array_view:: discard_data 메서드  
 이 보기는 현재 데이터를 삭제 합니다. 이 보기의 현재 내용을 대상에 복사 방지 하는 데 사용 되는 런타임에 대 한 최적화 힌트는 `accelerator_view` 하, 액세스 하 고 기존 콘텐츠 필요 하지 않은 경우 해당 사용을 권장 합니다. 이 메서드는 아무 restrict (amp) 컨텍스트에서 사용 하는 경우에  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewextentdatamembera-arrayviewextent-data-member"></a><a name="array_view__extent_data_member"></a>  array_view:: extent 데이터 멤버  
 `extent` 개체의 모양을 정의하는 `array_view` 개체를 가져옵니다.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearrayviewgetextentmethoda-arrayviewgetextent-method"></a><a name="array_view__get_extent_method"></a>  array_view:: get_extent 메서드  
 반환 된 [익스텐트](../../../parallel/amp/reference/extent-class-cpp-amp.md) 의 개체는 [array_view](../../../parallel/amp/reference/array-view-class.md) 개체입니다.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>반환 값  
 `extent` 개체의 `array_view` 개체입니다.  
  
##  <a name="a-namearrayviewgetrefmethoda-arrayviewgetref-method"></a><a name="array_view__get_ref_method"></a>  array_view:: get_ref 메서드  
 _Index로 인덱싱된 요소에 대 한 참조를 가져옵니다. 다른 인덱싱 연산자의 CPU에서 array_view에 액세스 하기 위한와 달리이 메서드 동기화 하지 않습니다 암시적으로이 array_view 내용을 cpu. Array_view 원격 위치에 액세스 하거나이 array_view 관련 된 복사 작업 수행 후 사용자가 명시적으로이 메서드를 호출 하기 전에 cpu array_view를 동기화 해야 합니다. 이렇게 하지 않으면 정의 되지 않은 동작이 발생 합니다.  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 _Index로 인덱싱된 요소에 대 한 참조  
  
##  <a name="a-namearrayviewgetsourceacceleratorviewmethoda-arrayviewgetsourceacceleratorview-method"></a><a name="array_view__get_source_accelerator_view_method"></a>  array_view:: get_source_accelerator_view 메서드  
 array_view의 데이터 소스 위치한는 accelerator_view를 반환 합니다. 이 API는 runtime_exception throw는 array_view 데이터 원본에 없는 경우  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-namearrayviewoperatoroperatora-arrayviewoperator-operator"></a><a name="array_view__operator___operator"></a>  array_view::operator() 연산자  
 매개 변수 또는 매개 변수에서 지정한 요소의 값을 반환 합니다.  
  
```  
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 요소의 위치입니다.  
  
 `_I0`  
 첫 번째 차원에서 인덱스입니다.  
  
 `_I1`  
 두 번째 차원 인덱스입니다.  
  
 `_I2`  
 세 번째 차원 인덱스입니다.  
  
 `_I`  
 요소의 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 매개 변수 또는 매개 변수에서 지정한 요소의 값입니다.  
  
##  <a name="a-namearrayviewoperatoratoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_at_operator"></a>  array_view:: operator] 연산자  
 매개 변수에 의해 지정 된 요소를 반환 합니다.  
  
```  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

 
value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Index`  
 인덱스입니다.  
  
 `_I`  
 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 인덱스에 요소 값 또는 `array_view` 가장 중요 한 차원에 프로젝션 합니다.  
  
##  <a name="a-namearrayviewoperatoreqoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_eq_operator"></a>  array_view:: operator = 연산자  
 지정 된 내용을 복사 [array_view](../../../parallel/amp/reference/array-view-class.md) 여기에 개체입니다.  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
  `array_view` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `array_view` 개체입니다.  
  
##  <a name="a-namearrayviewrankconstanta-arrayviewrank-constant"></a><a name="array_view__rank_constant"></a>  array_view:: rank 상수  
 차수를 저장 된 [array_view](../../../parallel/amp/reference/array-view-class.md) 개체입니다.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namearrayviewrefreshmethoda-arrayviewrefresh-method"></a><a name="array_view__refresh_method"></a>  array_view:: refresh 메서드  
 알립니다는 [array_view](../../../parallel/amp/reference/array-view-class.md) 외부에서 수정 되었으며 바인딩된 메모리 개체는 `array_view` 인터페이스입니다. 이 메서드를 호출 오래 된 모든 캐시 된 정보를 렌더링합니다.  
  
```  
void refresh() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewsectionmethoda-arrayviewsection-method"></a><a name="array_view__section_method"></a>  array_view:: section 메서드  
 하위 섹션을 반환 된 [array_view](../../../parallel/amp/reference/array-view-class.md) 지정된 된 origin 하 고, 필요에 따라 하에 있는 개체에는 지정 된 범위입니다.  
  
```  
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _E0) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_E0`  
 이 섹션의 범위는 가장 중요 한 구성 요소입니다.  
  
 `_E1`  
 이 섹션의 범위는 다음 기능을-가장 중요 한 구성 요소입니다.  
  
 `_E2`  
 이 섹션의 범위는 덜 중요 한 구성 요소입니다.  
  
 `_Ext`  
  [익스텐트](../../../parallel/amp/reference/extent-class-cpp-amp.md) 섹션의 범위를 지정 하는 개체입니다. 원점은 0입니다.  
  
 `_Idx`  
  [인덱스](../../../parallel/amp/reference/index-class.md) 출처의 위치를 지정 하는 개체입니다. 하위 범위의 나머지 부분입니다.  
  
 `_I0`  
 이 섹션의 원점의 가장 중요 한 구성 요소입니다.  
  
 `_I1`  
 이 섹션의 원점의 다음-에-가장 중요 한 구성 요소입니다.  
  
 `_I2`  
 이 섹션의 원점의 덜 중요 한 구성 요소입니다.  
  
 `_Rank`  
 섹션의 순위입니다.  
  
 `_Section_extent`  
  [익스텐트](../../../parallel/amp/reference/extent-class-cpp-amp.md) 섹션의 범위를 지정 하는 개체입니다.  
  
 `_Section_origin`  
  [인덱스](../../../parallel/amp/reference/index-class.md) 출처의 위치를 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 하위 섹션은 `array_view` 지정된 된 origin 하 고, 필요에 따라 하에 있는 개체에는 지정 된 범위입니다. 경우에는 `index` 개체가 지정 된 경우 인덱스에 있는 요소의 인덱스 보다 큰 경우에 연결 된 범위에서 모든 요소를 포함 하는 하위 섹션은 `index` 개체입니다.  
  
##  <a name="a-namearrayviewsourceacceleratorviewdatamembera-arrayviewsourceacceleratorview-data-member"></a><a name="array_view__source_accelerator_view_data_member"></a>  array_view:: source_accelerator_view 데이터 멤버  
 이 array_view 연관 된 원본 accelerator_view를 가져옵니다.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="a-namearrayviewsynchronizemethoda-arrayviewsynchronize-method"></a><a name="array_view__synchronize_method"></a>  array_view:: synchronize 메서드  
 모든 수정 내용이 동기화는 `array_view` 해당 원본 데이터에 다시 개체입니다.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Access_type`  
 의도 한 [access_type](concurrency%20namespace%20enums.md#access_type) 대상에 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md)합니다. 이 매개 변수는 기본값은 `access_type_read`합니다.  
  
##  <a name="a-namearrayviewsynchronizeasyncmethoda-arrayviewsynchronizeasync-method"></a><a name="array_view__synchronize_async_method"></a>  array_view:: synchronize_async 메서드  
 모든 수정 내용이 비동기적으로 동기화는 [array_view](../../../parallel/amp/reference/array-view-class.md) 해당 원본 데이터에 다시 개체입니다.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Access_type`  
 의도 한 [access_type](concurrency%20namespace%20enums.md#access_type) 대상에 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md)합니다. 이 매개 변수는 기본값은 `access_type_read`합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 완료 될 때까지 대기 하는 앞입니다.  
  
##  <a name="a-namearrayviewsynchronizetomethoda-arrayviewsynchronizeto-method"></a><a name="array_view__synchronize_to_method"></a>  array_view:: synchronize_to 메서드  
 지정 된 accelerator_view에이 array_view이 변경 사항은 동기화 합니다.  
  
```  
void synchronize_to(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Accl_view`  
 동기화 할 대상 accelerator_view 합니다.  
  
 `_Access_type`  
 대상 accelerator_view에 원하는 access_type 합니다. 이 매개 변수는 기본값을 access_type_read 합니다.  
  
##  <a name="a-namearrayviewsynchronizetoasyncmethoda-arrayviewsynchronizetoasync-method"></a><a name="array_view__synchronize_to_async_method"></a>  array_view:: synchronize_to_async 메서드  
 에 지정 된 accelerator_view이 array_view이 변경 사항은 비동기적으로 동기화 합니다.  
  
```  
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Accl_view`  
 동기화 할 대상 accelerator_view 합니다.  
  
 `_Access_type`  
 대상 accelerator_view에 원하는 access_type 합니다. 이 매개 변수는 기본값을 access_type_read 합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 완료 될 때까지 대기 하는 앞입니다.  
  
##  <a name="a-namearrayviewvaluetypedatamembera-arrayviewvaluetype-data-member"></a><a name="array_view__value_type_data_member"></a>  array_view:: value_type 데이터 멤버  
 값 형식에서 array_view 및 바인딩된 배열입니다.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="a-namearrayviewviewasmethoda-arrayviewviewas-method"></a><a name="array_view__view_as_method"></a>  array_view:: view_as 메서드  
 이 재해석 `array_view` 로 `array_view` 다른 차수입니다.  
  
```  
template <
    int _New_rank  
>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

 
template <
    int _New_rank  
>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>매개 변수  
 `_New_rank`  
 새 순위 `array_view` 개체입니다.  
  
 `_View_extent`  
 모양 변경 `extent`합니다.  
  
 `value_type`  
 데이터 형식에서 원래 요소의 [배열](../../../parallel/amp/reference/array-class.md) 개체와 반환 된 `array_view` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
  [array_view](../../../parallel/amp/reference/array-view-class.md) 생성 된 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 네임 스페이스 (c + + AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
