---
title: "Concurrency:: direct3d 네임 스페이스 함수 (AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
- amp/Concurrency::direct3d::imax
- amp/Concurrency::direct3d::is_timeout_disabled
- amp/Concurrency::direct3d::mad
- amp/Concurrency::direct3d::noise
- amp/Concurrency::direct3d::radians
- amp/Concurrency::direct3d::reversebits
- amp/Concurrency::direct3d::saturate
- amp/Concurrency::direct3d::smoothstep
- amp/Concurrency::direct3d::step
- amp/Concurrency::direct3d::umin
dev_langs: C++
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: ad00006c9ab4f25887cf28ed5b977551c35bda9e
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Concurrency:: direct3d 네임 스페이스 함수 (AMP)
||||  
|-|-|-|  
|[abs](#abs)|[clamp](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|||
|[d3d_access_lock](#d3d_access_lock)|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|  
|[firstbithigh](#firstbithigh)|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|  
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|  
|[mad](#mad)|[make_array](#make_array)|[노이즈](#noise)|  
|[라디안](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|  
|[saturate](#saturate)|[로그인](#sign)|[smoothstep](#smoothstep)|  
|[단계](#step)|[umax](#umax)|[umin](#umin)|  

## <a name="requirements"></a>요구 사항
**헤더:** amp.h **Namespace:** 동시성
  
##  <a name="abs"></a>  abs  
 인수의 절대값을 반환합니다.  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 인수의 절대값을 반환 합니다.  
  
##  <a name="clamp"></a>clamp  
 두 번째 및 세 번째 지정 된 인수에 의해 정의 된 범위를 제한 하는 첫 번째 지정 된 인수의 값을 계산 합니다.  
  
```  
inline float clamp(
    float _X,  
    float _Min,  
    float _Max) restrict(amp);

 
inline int clamp(
    int _X,  
    int _Min,  
    int _Max) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 고정 값  
  
 `_Min`  
 고정할 범위의 하 한입니다.  
  
 `_Max`  
 고정할 범위의 상한입니다.  
  
### <a name="return-value"></a>반환 값  
 Clamped 값 `_X`합니다.  
  
##  <a name="countbits"></a>countbits  
 _X의 비트를 집합의 개수  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부호 없는 정수 값  
  
### <a name="return-value"></a>반환 값  
 _X의 집합 비트 수를 반환합니다.  

## <a name="create_accelerator_view"></a>create_accelerator_view  
만듭니다는 [accelerator_view](accelerator-view-class.md) Direct3D 장치 인터페이스에 대 한 포인터에서 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
accelerator_view create_accelerator_view(  
    IUnknown * _D3D_device  
    queuing_mode _Qmode = queuing_mode_automatic);  
  
accelerator_view create_accelerator_view(  
    accelerator& _Accelerator,  
    bool _Disable_timeout  
    queuing_mode _Qmode = queuing_mode_automatic);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Accelerator`  
 만들려는 새 accelerator_view는 액셀러레이터 키입니다.  
  
 `_D3D_device`  
 Direct3D 장치 인터페이스에 대 한 포인터입니다.  
  
 `_Disable_timeout`  
 새로 만든된 accelerator_view에 대 한 제한 시간을 비활성화 해야 하는지 여부를 지정 하는 부울 매개 변수입니다. 이 Direct3D 장치를 만들기 위한 D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT 플래그에 해당 하며 운영 체제 Windows 제한 시간 탐지 및 복구 메커니즘 당 장치를 다시 설정 하지 않고 실행 하는 데 2 초 이상 걸리는 작업을 허용 해야 하는 경우를 나타내는 데 사용 됩니다. accelerator_view에서 시간이 많이 작업을 수행 하는 경우에이 플래그를 사용 하는 것이 좋습니다.  
  
 `_Qmode`  
 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) 새로 만든된 accelerator_view에 사용할 수 있습니다. 이 매개 변수는 기본값은 `queuing_mode_automatic`합니다.  
  
## <a name="return-value"></a>반환 값  
 `accelerator_view` 전달 된 Direct3D 장치 인터페이스를 통해 만든 개체입니다.  
  
## <a name="remarks"></a>설명  
 이 함수에서는 새 `accelerator_view` Direct3D 장치 인터페이스에 대 한 기존 포인터에서 개체입니다. 방법으로 매개 변수 참조 횟수는 늘어나지 함수 호출에 성공할 경우는 `AddRef` 인터페이스를 호출 합니다. DirectX 코드에서 더 이상 필요한 경우 개체를 안전 하 게 릴리스할 수 없습니다. 메서드 호출이 실패 하는 경우는 [runtime_exception](runtime-exception-class.md) throw 됩니다.  
  
 `accelerator_view` 이 함수를 사용 하 여 만든 개체는 스레드로부터 안전 합니다. 동시 사용을 동기화 해야는 `accelerator_view` 개체입니다. 동시 사용량 동기화 되지 않은 `accelerator_view` 개체와 원시 ID3D11Device 인터페이스 정의 되지 않은 동작이 발생 합니다.  
  
 사용 하는 경우에 D3D 디버그 계층을 사용 하 여 디버그 모드에서 자세한 오류 정보를 제공 하는 c + + AMP 런타임은 `D3D11_CREATE_DEVICE_DEBUG` 플래그입니다.  
  
  
##  <a name="d3d_access_lock"></a>d3d_access_lock  
 안전 하 게는 accelerator_view와 공유 리소스에 대 한 D3D 작업을 수행할 목적으로 accelerator_view에 대 한 잠금을 획득 합니다. accelerator_view 및 내부적으로이 accelerator_view와 관련 된 모든 c + + AMP 리소스 잠금을이 작업을 수행할 때 다른 스레드가 D3D 액세스 잠금을 보유 하는 동안 차단 됩니다. 이 잠금은 비재귀적: 이미 잠금을 보유 하는 스레드에서이 함수를 호출 하는 정의 되지 않은 동작입니다. accelerator_view 또는 D3D 액세스 잠금을 보유 하는 스레드에서 accelerator_view와 연결 된 모든 데이터 컨테이너에 대 한 작업을 수행 하는 정의 되지 않은 동작은 합니다. Scoped_d3d_access_lock, 범위 기반 D3D 액세스 잠금에 대 한 RAII 스타일 클래스를 참조 하십시오.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Av`  
 잠글 accelerator_view 합니다.  
  
##  <a name="d3d_access_try_lock"></a>d3d_access_try_lock  
 차단 하지 않고는 accelerator_view D3D 액세스 잠금을 획득 하려고 시도 합니다.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Av`  
 잠글 accelerator_view 합니다.  
  
### <a name="return-value"></a>반환 값  
 잠금이 설정 된 경우 true 또는 false 다른 스레드에 의해 현재 보유 하는 경우입니다.  
  
##  <a name="d3d_access_unlock"></a>d3d_access_unlock  
 주어진된 accelerator_view에 D3D 액세스 잠금을 해제 합니다. 호출 스레드는 accelerator_view에 잠금을 유지 하지 않으면 결과가 정의 되지 않습니다.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Av`  
 잠금이 해제 될는 accelerator_view 합니다.  
  
##  <a name="firstbithigh"></a>firstbithigh  
 최상위 비트로 시작 하 고 최하위 비트 전환 _X의 첫 번째 설정 비트의 위치를 가져옵니다.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 첫 번째 설정 비트의 위치  
  
##  <a name="firstbitlow"></a>firstbitlow  
 _X 최하위 비트로 시작 하 고 최상위 비트는 방향에 있는 첫 번째 설정 비트의 위치를 가져옵니다.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 첫 번째 설정 비트의 위치를 반환 합니다.  
  
##  <a name="get_buffer"></a>get_buffer  
 지정된 된 배열의 기본 Direct3D 버퍼 인터페이스를 가져옵니다.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;  
```  
  
### <a name="parameters"></a>매개 변수  
 `value_type`  
 배열 요소의 형식입니다.  
  
 `_Rank`  
 배열의 차수입니다.  
  
 `_Array`  
 Direct3D 버퍼 인터페이스에 있는 반환 하는 Direct3D accelerator_view에서 배열을 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 IUnknown 인터페이스 포인터를 Direct3D 버퍼 배열 내부에 해당 합니다.  
  
##  <a name="imax"></a>imax  
 인수의 최대 숫자 값 결정  
  
```  
inline int imax(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
 `_Y`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최대 숫자 값을 반환 합니다.  
  
##  <a name="imin"></a>imin  
 인수의 최소 숫자 값 결정  
  
```  
inline int imin(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
 `_Y`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최소 숫자 값을 반환 합니다.  
  
##  <a name="is_timeout_disabled"></a>is_timeout_disabled  
 시간 제한 지정된 accelerator_view를 사용할 경우를 나타내는 부울 플래그를 반환 합니다. 이 Direct3D 장치를 만들기 위한 D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT 플래그에 해당합니다.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Accelerator_view`  
 제한 시간 설정을 비활성화 있는 accelerator_view 쿼리할 수입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 accelerator_view에 대 한 제한 시간에 사용할 수 없습니다를 나타내는 부울 플래그입니다.  
  
##  <a name="mad"></a>mad  
 첫 번째 및 두 번째 지정 된 인수를의 곱을 계산 하는 세 번째 지정 된 인수를 추가 합니다.  
  
```  
inline float mad(
    float _X,  
    float _Y,  
    float _Z) restrict(amp);

 
inline double mad(
    double _X,  
    double _Y,  
    double _Z) restrict(amp);

 
inline int mad(
    int _X,  
    int _Y,  
    int _Z) restrict(amp);

 
inline unsigned int mad(
    unsigned int _X,  
    unsigned int _Y,  
    unsigned int _Z) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 첫 번째 인수를 지정 합니다.  
  
 `_Y`  
 두 번째 인수를 지정 합니다.  
  
 `_Z`  
 세 번째 인수를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 The result of `_X` * `_Y` + `_Z`.  
  
##  <a name="make_array"></a>make_array  
 Direct3D 버퍼 인터페이스 포인터에서 배열을 만듭니다.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,  
    const Concurrency::accelerator_view& _Rv,  
    IUnknown* _D3D_buffer)  ;  
```  
  
### <a name="parameters"></a>매개 변수  
 `value_type`  
 만들려는 배열의 요소 형식입니다.  
  
 `_Rank`  
 만들려는 배열의 차수입니다.  
  
 `_Extent`  
 배열 집계의 모양을 설명 하는 범위.  
  
 `_Rv`  
 만들려는 배열의 D3D 엑셀 러 레이 터 보기입니다.  
  
 `_D3D_buffer`  
 배열에서 만들 D3D 버퍼의 IUnknown 인터페이스 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 제공된 된 Direct3D 버퍼를 사용 하 여 만든 배열입니다.  
  
##  <a name="noise"></a>노이즈  
 Perlin 노이즈 알고리즘을 사용하여 임의의 값을 생성합니다.  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 Perlin 노이즈를 생성하는 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 -1과 1 사이의 범위 내에서 Perlin 노이즈 값을 반환합니다.  
  
##  <a name="radians"></a>라디안  
 _X 각도에서 라디안으로 변환  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 각도에서 라디안으로 변환한 _X를 반환합니다.  
  
##  <a name="rcp"></a>rcp  
 빠른 근사값을 사용 하 여 지정된 된 인수의 역을 계산 합니다.  
  
```  
inline float rcp(float _X) restrict(amp);

 
inline double rcp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 역을 계산 하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인수 역입니다.  
  
##  <a name="reversebits"></a>reversebits  
 _X의 비트의 순서를 반대로 바꿉니다.  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부호 없는 정수 값  
  
### <a name="return-value"></a>반환 값  
 _X의 반대로 바뀐 비트 순서 값을 반환합니다.  
  
##  <a name="saturate"></a>saturate  
 0 또는 1의 범위 내 _X 고정  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 0 - 1의 범위 내로 제한된 _X를 반환합니다.  
  
##  <a name="sign"></a>로그인  
 지정된 된 인수의 부호를 결정합니다.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 인수의 기호입니다.  
  
##  <a name="smoothstep"></a>smoothstep  
 _X가 [_Min, _Max] 범위에 경우에 0과 1 사이의 부드러운 Hermite 보간을 반환 합니다.  
  
```  
inline float smoothstep(
    float _Min,  
    float _Max,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Min`  
 부동 소수점 값  
  
 `_Max`  
 부동 소수점 값  
  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X가 _Min보다 작은 경우 0을, _X가 _Max보다 큰 경우 1을 반환합니다. 그렇지 않으면, _X가 [_Min, _Max] 범위에 있는 경우 0과 1 사이의 값입니다.  
  
##  <a name="step"></a>단계  
 두 값을 반환 하는 0 또는 1을 기반으로 어떤 값이 큰 비교  
  
```  
inline float step(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Y`  
 부동 소수점 값  
  
 `_X`  
 부동 소수점 값  
  
### <a name="return-value"></a>반환 값  
 _X가 _Y보다 큰 경우 1을 반환합니다. 그렇지 않으면, 0을 반환합니다.  
  
##  <a name="umax"></a>umax  
 인수의 최대 숫자 값 결정  
  
```  
inline unsigned int umax(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
 `_Y`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최대 숫자 값을 반환 합니다.  
  
##  <a name="umin"></a>umin  
 인수의 최소 숫자 값 결정  
  
```  
inline unsigned int umin(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>매개 변수  
 `_X`  
 정수 값  
  
 `_Y`  
 정수 값  
  
### <a name="return-value"></a>반환 값  
 인수의 최소 숫자 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)

