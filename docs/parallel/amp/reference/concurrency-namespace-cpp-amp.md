---
title: "동시성 Namespace (c + + AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/Concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 38c3154244b163202bcb8e271f96b393231247ca
ms.lasthandoff: 03/17/2017

---
# <a name="concurrency-namespace-c-amp"></a>Concurrency 네임스페이스(C++ AMP)
클래스와 데이터 병렬 하드웨어에서 c + + 코드의 실행을 가속화 하는 함수를 제공 합니다. 자세한 내용은 참조 [c + + AMP 개요](../cpp-amp-overview.md)  
  
## <a name="syntax"></a>구문  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="namespaces"></a>네임스페이스  
  
|이름|설명|  
|----------|-----------------|  
|[Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)|D3D 상호 운용성을 지 원하는 기능을 제공 합니다. 완벽 한 리소스 사용 하 여 D3D AMP 코드에는 계산에 대 한 중간 중복 복사본을 만들지 않고 amp에서 D3D 코드에서 만든 리소스의 사용이 가능 합니다. 증분 DirectX 응용 프로그램의 계산 집약적인 섹션을 가속화 하 D3D API를 사용 하 여 AMP 계산에서 생성 된 데이터에 c + + AMP를 사용할 수 있습니다.|  
|[Concurrency::fast_math 네임스페이스](concurrency-fast-math-namespace.md)|가 작동 하는 `fast_math` 네임 스페이스 C99와 호환 되지 않습니다. 각 함수는 단 정밀도 버전만 제공 됩니다. 이러한 함수는 해당 함수에 보다 빠르게 있는 DirectX 내장 함수를 사용 하 여는 `precise_math` 네임 스페이스를 액셀러레이터의 연장된 배정밀 지원 필요 하지 않지만 덜 정확 하 게 구성 하 고 있습니다. 두 가지 버전의 소스 수준 코드와의 호환성 C99;에 대 한 각 함수 두 버전 모두 수행 하 고 단 정밀도 값을 반환 합니다.|  
|[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)|그래픽 프로그래밍에 대 한 형식 및 설계 된 함수를 제공 합니다.|  
|[Concurrency::precise_math 네임스페이스](concurrency-precise-math-namespace.md)|가 작동 하는 `precise_math` 네임 스페이스 C99 호환 됩니다. 각 함수의 버전을 단 정밀도 및 배정밀 모두 포함 됩니다. 이러한 함수-여기에 단 정밀도 함수 포함 됩니다.-액셀러레이터에서 확장 된 이중 정밀도 지원이 필요 합니다.|  
  
### <a name="classes"></a>클래스  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator 클래스](accelerator-class.md)|물리적 DP 액세스에 최적화 된 계산 노드는 추상화를 나타냅니다.|  
|[accelerator_view 클래스](accelerator-view-class.md)|C + + AMP 데이터 병렬 액셀러레이터에는 가상 장치 추상화를 나타냅니다.|  
|[accelerator_view_removed 클래스](accelerator-view-removed-class.md)|Windows 시간 초과 검색-및-복구 메커니즘으로 인해 내부 DirectX 호출이 실패할 때 throw 되는 예외입니다.|  
|[array 클래스](array-class.md)|데이터에 집계는 `accelerator_view` 표 도메인에 있습니다. 표 도메인에 있는 각 요소에 대 한 변수 모음입니다. 각 변수는 c + + 형식에 해당 하는 값을 보유 합니다.|  
|[array_view 클래스](array-view-class.md)|배열에 있는 데이터에 대 한 뷰를 나타내는\<T, N >.|  
|[completion_future 클래스](completion-future-class.md)|C + + AMP 비동기 작업에 해당 하는 미래를 나타냅니다.|  
|[extent 클래스](extent-class.md)|0의 원점이 N 차원 공간의 경계를 지정 하는 N 정수 값의 벡터를 나타냅니다. 좌표는 벡터의 값에서 가장 중요 한 최하위에 정렬 됩니다. 예를 들어 데카르트 3 차원 공간 익스텐트 벡터 (7,5,3) 0에서 7로 y 좌표 범위는 0에서 5 사이의 정수 z 좌표 및 0에서 3 사이의 정수에 대 한 x 좌표 공간을 나타냅니다.|  
|[index 클래스](index-class.md)|N 차원는 인덱스 위치를 정의합니다.|  
|[invalid_compute_domain 클래스](invalid-compute-domain-class.md)|런타임에에서 지정 된 계산 도메인을 사용 하 여 커널을 시작할 수 없는 경우 throw 되는 예외는 `parallel_for_each` 호출 사이트입니다.|  
|[out_of_memory 클래스](out-of-memory-class.md)|시스템 또는 장치 메모리 부족으로 인해 메서드가 실패할 때 throw 되는 예외입니다.|  
|[runtime_exception 클래스](runtime-exception-class.md)|C + + AMP 라이브러리의 예외에 대 한 기본 형식입니다.|  
|[tile_barrier 클래스](tile-barrier-class.md)|시스템에서 만들 수만 있으며에 전달 하는 기능 클래스를 바둑판식으로 배열 된 `parallel_for_each` 의 일환으로 람다는 `tiled_index` 매개 변수입니다. 한 가지 방법은 제공 `wait()`, 목적인 실행 스레드 그룹 (타일)에서 실행 되는 스레드를 동기화 하는 것입니다.|  
|[tiled_extent 클래스](tiled-extent-class.md)|A `tiled_extent` 개체는 `extent`&1; 차원, 차원, 또는&3; 차원 타일로 익스텐트 공간 세분 하는&1; ~&3; 개의 차원 개체입니다.|  
|[tiled_index 클래스](tiled-index-class.md)|에 대 한 인덱스를 제공 된 `tiled_grid` 개체입니다. 이 클래스에 로컬 타일 원점을 기준으로 하 고 전역 원점을 기준으로 요소에 액세스 하는 속성이 있습니다.|  
|[uninitialized_object 클래스](uninitialized-object-class.md)|초기화 되지 않은 개체를 사용 하는 경우 throw 되는 예외입니다.|  
|[unsupported_feature 클래스](unsupported-feature-class.md)|지원 되지 않는 기능을 사용할 때 throw 되는 예외입니다.|  
  
### <a name="enumerations"></a>열거형  
  
|이름|설명|  
|----------|-----------------|  
|[access_type 열거형](concurrency-namespace-enums-amp.md#access_type)|데이터 액세스 유형을 지정합니다.|  
|[queuing_mode 열거형](concurrency-namespace-enums-amp.md#queuing_mode)|액셀러레이터에서 지원 되는 큐 모드를 지정 합니다.|  
  
### <a name="operators"></a>연산자  
  
|연산자|설명|  
|--------------|-----------------|  
|[연산자 = = 연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|지정 된 데이터 구조 같은지 여부를 결정 합니다.|  
|[연산자! = 연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator_neq)|지정 된 데이터 구조체가 같지 않은지 여부를 결정 합니다.|  
|[operator + 연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator_add)|지정된 된 인수의 component-wise 합을 계산 합니다.|  
|[operator-연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator-)|지정된 된 인수 간의 component-wise 차이 계산 합니다.|  
|[operator * 연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator_star)|지정 된 인수가 component-wise 곱을 계산 합니다.|  
|[operator / 연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator_div)|지정된 된 인수 component-wise 몫을 계산합니다.|  
|[operator % 연산자 (c + + AMP)](concurrency-namespace-operators-amp.md#operator_mod)|두 번째는 지정 된 인수에 의해 지정된 된 첫 번째 인수의 모듈러스를 계산합니다.|  
  
### <a name="functions"></a>함수  
  
|이름|설명|  
|----------|-----------------|  
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|모든 메모리 액세스 완료 될 때까지 타일에 있는 모든 스레드의 실행을 차단 합니다.|  
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|C + + AMP 런타임을 초기화 하지 않습니다.|  
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|오버로드됨. 첫 번째 지정 된 값으로 지정된 된 위치에 저장 된 값을 비교 하는 경우 지정된 된 두 번째 값은 원자성 작업으로 동일한 위치에 저장 됩니다.|  
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|오버로드됨. 원자 단위 연산으로 지정된 된 값으로 지정된 된 위치에 저장 된 값을 설정 합니다.|  
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|오버로드됨. 원자 단위 연산으로 지정된 된 값과 값의 합계를 지정된 된 위치에 저장 된 값을 설정 합니다.|  
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|오버로드됨. 비트 지정된 된 위치에 저장 된 값을 설정 `and` 과 원자 단위 연산으로 지정된 된 값입니다.|  
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|오버로드됨. 지정된 된 위치에 저장 하 고 원자성 작업으로 동일한 위치에는 결과 저장 하는 값을 감소 시킵니다.|  
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|오버로드됨. 지정된 된 위치에 저장 된 값이 증가 하 고 원자성 작업으로 동일한 위치에 결과 저장 합니다.|  
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|오버로드됨. 더 큰 숫자 지정된 된 위치에 저장 된 값을 설정 값과 원자 단위 연산으로 지정된 된 값입니다.|  
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|오버로드됨. 더 작은 숫자 지정된 된 위치에 저장 된 값을 설정 값과 원자 단위 연산으로 지정된 된 값입니다.|  
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|오버로드됨. 비트 지정된 된 위치에 저장 된 값을 설정 `or` 과 원자 단위 연산으로 지정된 된 값입니다.|  
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|오버로드됨. 원자 단위 연산으로 지정된 된 값과 값의 차이 지정된 된 위치에 저장 된 값을 설정 합니다.|  
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|오버로드됨. 비트 지정된 된 위치에 저장 된 값을 설정 `xor` 과 원자 단위 연산으로 지정된 된 값입니다.|  
|[copy](concurrency-namespace-functions-amp.md#copy)|C + + AMP 개체를 복사합니다. 모든 동기 데이터 전송 요구 사항이 충족 됩니다. 코드에서 가속기 코드를 실행 하는 경우 데이터를 복사할 수 없습니다. 이 함수의 일반적인 형태 `copy(src, dest)`합니다.|  
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|C + + AMP 개체를 복사 하 고 반환 [completion_future](completion-future-class.md) 에서 대기한 수입니다. 액셀러레이터에서 코드를 실행 하는 경우 데이터를 복사할 수 없습니다. 이 함수의 일반적인 형태 `copy(src, dest)`합니다.|  
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|포함 된 함수 실행을 중단는 `restrict(amp)` 제약 조건 절.|  
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Visual Studio에 서식이 지정 된 문자열을 인쇄 **출력** 창과 발생은 [runtime_exception](runtime-exception-class.md) 동일한 서식이 있는 예외는 문자열입니다.|  
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Visual Studio에 서식이 지정 된 문자열을 인쇄 **출력** 창입니다. 포함 된 함수에서 호출 되어는 `restrict(amp)` 제약 조건 절.|  
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|모든 글로벌 메모리에 액세스할 때까지 타일에 있는 모든 스레드의 실행을 차단 완료 되었습니다.|  
|[parallel_for_each 함수 (c + + AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|계산 도메인 간에 함수를 실행 합니다.|  
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|실행 될 때까지 타일의 모든 스레드를 차단 `tile_static` 메모리 액세스 완료 되었습니다.|  
  
## <a name="constants"></a>상수  
  
|이름|설명|  
|----------|-----------------|  
|[HLSL_MAX_NUM_BUFFERS 상수](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|DirectX에 의해 허용 되는 버퍼의 최대 수입니다.|  
|[MODULENAME_MAX_LENGTH 상수](concurrency-namespace-constants-amp.md#modulename_max_length)|모듈 이름의 최대 길이 저장합니다. 이 값은 컴파일러와 런타임에서 동일 해야 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(C++ AMP)](reference-cpp-amp.md)




