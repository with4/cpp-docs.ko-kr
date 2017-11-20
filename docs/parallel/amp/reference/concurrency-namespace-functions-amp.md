---
title: "동시성 네임 스페이스 함수 (AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::all_memory_fence
- amp/Concurrency::atomic_compare_exchange
- amp/Concurrency::atomic_fetch_dec
- amp/Concurrency::atomic_fetch_max
- amp/Concurrency::atomic_fetch_min
- amp/Concurrency::copy
- amp/Concurrency::direct3d_abort
- amp/Concurrency::direct3d_printf
- amp/Concurrency::global_memory_fence
- amp/Concurrency::tile_static_memory_fence
dev_langs: C++
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 26361befb1ca245a9efe8dd0db4ba4f30129bda6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="concurrency-namespace-functions-amp"></a>동시성 네임 스페이스 함수 (AMP)
||||  
|-|-|-|  
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|  
|[atomic_exchange 함수 (c + + AMP)](#atomic_exchange)|[atomic_fetch_add 함수 (c + + AMP)](#atomic_fetch_add)|[atomic_fetch_and 함수 (c + + AMP)](#atomic_fetch_and)|  
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|  
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or 함수 (c + + AMP)](#atomic_fetch_or)|[atomic_fetch_sub 함수 (c + + AMP)](#atomic_fetch_sub)|  
|[atomic_fetch_xor 함수 (c + + AMP)](#atomic_fetch_xor)|[copy](#copy)|[copy_async](#copy_async)|  
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|  
|[global_memory_fence](#global_memory_fence)|[parallel_for_each 함수 (c + + AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|  
  
##  <a name="all_memory_fence"></a>all_memory_fence  
 모든 메모리 액세스가 완료 될 때까지 타일에 있는 모든 스레드의 실행을 차단 합니다. 이렇게 하면 모든 메모리 액세스에 스레드 타일의 다른 스레드를 볼 수 있으며 프로그램 순서로 실행 됩니다.  
  
```  
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Barrier`  
 `tile_barrier` 개체입니다.  
  
##  <a name="amp_uninitialize"></a>amp_uninitialize  
 C + + AMP 런타임 초기화를 취소 합니다. 응용 프로그램 수명 동안 여러 번이이 함수를 호출 하는 것이 올바릅니다. 이 함수를 호출 하는 모든 c + + AMP API afer 호출 c + + AMP 런타임 다시 초기화 됩니다. Note는이 함수 호출에서 c + + AMP 개체를 사용 하 고 따라서 이렇게 하면 정의 되지 않은 동작이 발생 합니다. 또한이 함수 및 기타 AMP Api 호출 하는 동시에 수행할 수 없습니다 및 정의 되지 않은 동작이 발생 합니다.  
  
```  
void __cdecl amp_uninitialize();
```  
  
##  <a name="atomic_compare_exchange"></a>atomic_compare_exchange  
 원자적으로 비교 하 여 메모리 위치에 저장 된 값에에서 지정 된 두 번째는 지정 된 인수 값과 같음에 대 한 첫 번째 인수 및 값이 동일 하면 메모리 위치의 값으로 변경 된 경우는의 세 번째 인수를 지정 합니다.  
  
```  
inline bool atomic_compare_exchange(
    _Inout_ int* _Dest,  
    _Inout_ int* _Expected_value,  
    int value  
    ) restrict(amp)

 
inline bool atomic_compare_exchange(
    _Inout_ unsigned int* _Dest,  
    _Inout_ unsigned int* _Expected_value,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 비교 되는 값 중 하나에서 위치 읽고 새 값, 있는 경우를 저장할 수 있습니다.  
  
 `_Expected_value`  
 비교할 두 번째 값을 읽어올 위치입니다.  
  
 `value`  
 에 의해 지정 된 메모리 위치에 저장할 값 `_Dest` 경우 `_Dest` 같으면 `_Expected_value`합니다.  
  
### <a name="return-value"></a>반환 값  
 작업에 성공하면 `true`이고, 그렇지 않으면 `false`입니다.  
  

##  <a name="atomic_exchange"></a>atomic_exchange 함수 (c + + AMP)  
 원자 단위 작업으로 대상 위치의 값을 설정합니다.  
  
```  
inline int atomic_exchange(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_exchange(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)

 
inline float atomic_exchange(
    _Inout_ float* _Dest,  
    float value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 대상 위치에 대한 포인터입니다.  
  
 `value`  
 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 대상 위치의 원본 값입니다.  
  

##  <a name="atomic_fetch_add"></a>atomic_fetch_add 함수 (c + + AMP)  
 원자 값 메모리 위치의 값을 추가 합니다.  
  
```  
inline int atomic_fetch_add(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_add(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 메모리 위치에 대한 포인터입니다.  
  
 `value`  
 추가할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치의 원본 값입니다.  
  
##  <a name="atomic_fetch_and"></a>atomic_fetch_and 함수 (c + + AMP)  
 값과 메모리 위치의 값의 비트 AND 연산을 원자 단위로 수행 합니다.  
  
```  
inline int atomic_fetch_and(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_and(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 메모리 위치에 대한 포인터입니다.  
  
 `value`  
 비트 AND 계산에 사용할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치의 원본 값입니다.  
  
##  <a name="atomic_fetch_dec"></a>atomic_fetch_dec  
 원자적으로 감소 값에 저장 된 지정된 된 메모리 위치 합니다.  
  
```  
inline int atomic_fetch_dec(_Inout_ int* _Dest  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 감소 시킬 값의 메모리 내의 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치에 저장 된 원래 값입니다.  
  
##  <a name="atomic_fetch_inc"></a>atomic_fetch_inc  
 원자적으로 지정된 된 메모리 위치에 저장 된 값을 증가 시킵니다.  
  
```  
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

 
inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 메모리 증가 시킬 값의 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치에 저장 된 원래 값입니다.  
  
##  <a name="atomic_fetch_max"></a>atomic_fetch_max  
 원자적으로 첫 번째 인수 및 두 번째 인수에 지정 된 값에 지정 된 메모리 위치에 저장 된 값 간의 최대 값을 계산 하 고 동일한 메모리 위치에 저장 합니다.  
  
```  
inline int atomic_fetch_max(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_max(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 비교 되는 값 중 하나에서 위치를 읽고 두 값의 최대를 저장할 수 있습니다.  
  
 `value`  
 지정된 된 위치에 있는 값에 비교할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치 위치에 저장 된 원래 값입니다.  
  
##  <a name="atomic_fetch_min"></a>atomic_fetch_min  
 원자적으로 첫 번째 인수 및 두 번째 인수에 지정 된 값에 지정 된 메모리 위치에 저장 된 값 사이의 최소 값을 계산 하 고 동일한 메모리 위치에 저장 합니다.  
  
```  
inline int atomic_fetch_min(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_min(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 비교 되는 값 중 하나에서 위치를 읽고 두 값의 최소를 저장할 수 있습니다.  
  
 `value`  
 지정된 된 위치에 있는 값에 비교할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치 위치에 저장 된 원래 값입니다.  
  
##  <a name="atomic_fetch_or"></a>atomic_fetch_or 함수 (c + + AMP)  
 값 및 메모리 위치의 값으로 비트 OR 연산을 원자 단위로 수행합니다.  
  
```  
inline int atomic_fetch_or(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_or(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 메모리 위치에 대한 포인터입니다.  
  
 `value`  
 비트 OR 계산에 사용할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치의 원본 값입니다.  
  
##  <a name="atomic_fetch_sub"></a>atomic_fetch_sub 함수 (c + + AMP)  
 원자적으로 메모리 위치에서 값을 뺍니다.  
  
```  
inline int atomic_fetch_sub(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_sub(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 대상 위치에 대한 포인터입니다.  
  
 `value`  
 뺄 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치의 원본 값입니다.  
  
##  <a name="atomic_fetch_xor"></a>atomic_fetch_xor 함수 (c + + AMP)  
 원자적으로 peforms 메모리 위치 및 값의 비트 XOR 작업 합니다.  
  
```  
inline int atomic_fetch_xor(
    _Inout_ int* _Dest,  
    int value  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_xor(
    _Inout_ unsigned int* _Dest,  
    unsigned int value  
    ) restrict(amp)
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 메모리 위치에 대한 포인터입니다.  
  
 `value`  
 XOR 계산에 사용할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 위치의 원본 값입니다.  
  
##  <a name="copy"></a>  copy  
 C + + AMP 개체를 복사합니다. 모든 동기 데이터 전송 요구 사항이 충족 됩니다. 액셀러레이터에서 코드를 실행할 때 데이터를 복사할 수 없습니다. 이 함수는 일반적인 형태의 `copy(src, dest)`합니다.  
  
```  
template <typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,  
    array<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,
     OutputIterator _DestIter);

 
template <typename value_type, int _Rank>  
void copy(
    const array<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<const value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<const value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst, 
    InputIterator _SrcLast,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
void copy(
    InputIterator _SrcFirst,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
void copy(
    const array_view<value_type, _Rank>& _Src,
    OutputIterator _DestIter);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 복사할 대상 개체입니다.  
  
 `_DestIter`  
 대상에서 시작 위치를 사용 하는 출력 반복기입니다.  
  
 `InputIterator`  
 입력된 interator의 형식입니다.  
  
 `OutputIterator`  
 출력 반복기의 형식입니다.  
  
 `_Rank`  
 복사할 개체 또는 복사할 대상 개체의 순위입니다.  
  
 `_Src`  
 복사할 개체입니다.  
  
 `_SrcFirst`  
 소스 컨테이너에는 시작 반복기입니다.  
  
 `_SrcLast`  
 소스 컨테이너에 사용 되는 끝 반복기입니다.  
  
 `value_type`  
 복사 된 요소의 데이터 형식입니다.  
  
##  <a name="copy_async"></a>copy_async  
 c + + AMP 개체를 복사 하 고 반환 된 [completion_future](completion-future-class.md) 대기한 수 있는 개체입니다. 액셀러레이터에서 코드를 실행할 때 데이터를 복사할 수 없습니다.  이 함수는 일반적인 형태의 `copy(src, dest)`합니다.  
  
```  
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,  
    array<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst,  
    array<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src, OutputIterator _DestIter);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,  
    array<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename InputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(InputIterator _SrcFirst,  
    array_view<value_type, _Rank>& _Dest);

 
template <typename OutputIterator, typename value_type, int _Rank>  
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src, OutputIterator _DestIter);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Dest`  
 복사할 대상 개체입니다.  
  
 `_DestIter`  
 대상에서 시작 위치를 사용 하는 출력 반복기입니다.  
  
 `InputIterator`  
 입력된 interator의 형식입니다.  
  
 `OutputIterator`  
 출력 반복기의 형식입니다.  
  
 `_Rank`  
 복사할 개체 또는 복사할 대상 개체의 순위입니다.  
  
 `_Src`  
 복사할 개체입니다.  
  
 `_SrcFirst`  
 소스 컨테이너에는 시작 반복기입니다.  
  
 `_SrcLast`  
 소스 컨테이너에 사용 되는 끝 반복기입니다.  
  
 `value_type`  
 복사 된 요소의 데이터 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 A `future<void>` 에서 대기한 수입니다.  
  
##  <a name="direct3d_abort"></a>direct3d_abort  
 `restrict(amp)` 제한 절이 있는 함수의 실행을 중단합니다. AMP 런타임이 호출을 감지 하면 발생 한 [runtime_exception](runtime-exception-class.md) 오류 메시지와 함께 예외 "Reference Rasterizer: Shader abort 명령 적중"입니다.  
  
```  
void direct3d_abort() restrict(amp);
```  
  
##  <a name="direct3d_errorf"></a>direct3d_errorf  
 Visual Studio 출력 창에 서식이 지정 된 문자열을 인쇄합니다. 사용 하는 함수에서 호출 되는 `restrict(amp)` 제한 절. AMP 런타임이 호출을 감지 하면 발생 한 [runtime_exception](runtime-exception-class.md) 동일한 서식 문자열을 사용 하 여 예외입니다.  
  
```  
void direct3d_errorf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="direct3d_printf"></a>direct3d_printf  
 Visual Studio 출력 창에 서식이 지정 된 문자열을 인쇄합니다. 사용 하는 함수에서 호출 되는 `restrict(amp)` 제한 절.  
  
```  
void direct3d_printf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="global_memory_fence"></a>global_memory_fence  
 모든 전역 메모리에 액세스 될 때까지 타일에 있는 모든 스레드의 실행을 차단 완료 되었습니다. 이렇게 하면 전역 메모리 액세스에 스레드 타일의 다른 스레드를 볼 수 있으며 프로그램 순서로 실행 됩니다.  
  
```  
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Barrier`  
 Tile_barrier 개체  
  
##  <a name="parallel_for_each"></a>parallel_for_each 함수 (c + + AMP)  
 계산 도메인에서 함수를 실행합니다. 자세한 내용은 참조 [c + + AMP 개요](../../../parallel/amp/cpp-amp-overview.md)합니다.  
  
```  
template <int _Rank, typename _Kernel_type>  
void parallel_for_each(
    const extent<_Rank>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
     const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

 
template <int _Dim0, typename _Kernel_type>  
void parallel_for_each(
    const tiled_extent<_Dim0>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Rank, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const extent<_Rank>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, int _Dim1, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,  
    const _Kernel_type& _Kernel);

 
template <int _Dim0, typename _Kernel_type>  
void parallel_for_each(
    const accelerator_view& _Accl_view,  
    const tiled_extent<_Dim0>& _Compute_domain,  
    const _Kernel_type& _Kernel);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Accl_view`  
 `accelerator_view` 에서 병렬 계산을 실행 하는 개체입니다.  
  
 `_Compute_domain`  
 `extent` 계산에 대 한 데이터를 포함 하는 개체입니다.  
  
 `_Dim0`  
 차원에서 `tiled_extent` 개체입니다.  
  
 `_Dim1`  
 차원에서 `tiled_extent` 개체입니다.  
  
 `_Dim2`  
 차원에서 `tiled_extent` 개체입니다.  
  
 `_Kernel`  
 형식의 인수를 사용 하는 람다 또는 함수 개체 "인덱스\<_Rank >" 하 고 병렬 계산을 수행 합니다.  
  
 `_Kernel_type`  
 람다 또는 함수입니다.  
  
 `_Rank`  
 범위의 순위입니다.  
  
##  <a name="tile_static_memory_fence"></a>tile_static_memory_fence  
 모든 때까지 타일에 있는 모든 스레드의 실행을 차단 미해결 `tile_static` 메모리 액세스 완료 되었습니다. 이렇게 하면 `tile_static` 메모리 액세스는 스레드 타일의 다른 스레드를 볼 수 있으며 액세스 프로그램 순서로 실행 됩니다.  
  
```  
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Barrier`  
 Tile_barrier 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
