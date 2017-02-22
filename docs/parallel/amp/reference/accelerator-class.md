---
title: "accelerator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator 클래스"
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# accelerator 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

액셀러레이터 키에는 데이터 병렬 컴퓨팅을 위한 최적화 된 하드웨어 기능입니다. 액셀러레이터 키 (예: GPU), PCIe 버스에 연결 된 장치 이거나 주 CPU에 설정 하는 확장 된 명령 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator:: accelerator 생성자](#accelerator__accelerator_constructor)|`accelerator` 클래스의 새 인스턴스를 초기화합니다.|  
|[accelerator:: ~ accelerator 소멸자](#accelerator___dtoraccelerator_destructor)|소멸은 `accelerator` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator:: create_view 메서드](#accelerator__create_view_method)|만들고 반환는 `accelerator_view` 이 액셀러레이터의 개체입니다.|  
|[accelerator:: get_all 메서드](#accelerator__get_all_method)|벡터를 반환 `accelerator` 사용 가능한 모든 액셀러레이터를 나타내는 개체입니다.|  
|[accelerator:: get_auto_selection_view 메서드](#accelerator__get_auto_selection_view_method)|자동 선택 반환 `accelerator_view`합니다.|  
|[accelerator:: get_dedicated_memory 메서드](#accelerator__get_dedicated_memory_method)|반환에 대 한 전용된 된 메모리는 `accelerator`, (킬로바이트)에서입니다.|  
|[accelerator:: get_default_cpu_access_type 메서드](#accelerator__get_default_cpu_access_type_method)|기본 반환 [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 이 액셀러레이터에서 생성 하는 버퍼입니다.|  
|[accelerator:: get_default_view 메서드](#accelerator__get_default_view_method)|기본 반환 `accelerator_view` 연관 된 개체는 `accelerator`합니다.|  
|[accelerator:: get_description 메서드](#accelerator__get_description_method)|에 대 한 간단한 설명을 반환는 `accelerator` 장치입니다.|  
|[accelerator:: get_device_path 메서드](#accelerator__get_device_path_method)|장치 경로 반환합니다.|  
|[accelerator:: get_has_display 메서드](#accelerator__get_has_display_method)|결정 여부는 `accelerator` 디스플레이에 연결 됩니다.|  
|[accelerator:: get_is_debug 메서드](#accelerator__get_is_debug_method)|결정 여부는 `accelerator` DEBUG 레이어가 확장 오류 보고에 대 한 활성화 했습니다.|  
|[accelerator:: get_is_emulated 메서드](#accelerator__get_is_emulated_method)|확인 여부는 `accelerator` 에뮬레이트됩니다.|  
|[accelerator:: get_supports_cpu_shared_memory 메서드](#accelerator__get_supports_cpu_shared_memory_method)|확인 여부는 `accelerator` 공유 메모리 지원|  
|[accelerator:: get_supports_double_precision 메서드](#accelerator__get_supports_double_precision_method)|결정 여부는 `accelerator` 디스플레이에 연결 됩니다.|  
|[accelerator:: get_supports_limited_double_precision 메서드](#accelerator__get_supports_limited_double_precision_method)|확인 여부는 `accelerator` 이중 정밀도 수치를 제한적으로 지원 합니다.|  
|[accelerator:: get_version 메서드](#accelerator__get_version_method)|버전을 반환 된 `accelerator`합니다.|  
|[accelerator:: set_default 메서드](#accelerator__set_default_method)|기본 액셀러레이터의 경로 반환합니다.|  
|[accelerator:: set_default_cpu_access_type 메서드](#accelerator__set_default_cpu_access_type_method)|기본 CPU 설정 [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 배열 및이 만든 암시적 메모리 할당에 `accelerator`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator:: operator! = 연산자](#accelerator__operator_neq_operator)|비교 하 여 `accelerator` 반환 하 고 개체와 다른 `false` 않으면는 동일 합니다; 그렇지 않으면 반환 `true`합니다.|  
|[accelerator:: operator = 연산자](#accelerator__operator_eq_operator)|지정 된 내용을 복사 `accelerator` 여기에 개체입니다.|  
|[accelerator:: operator = = 연산자](#accelerator__operator_eq_eq_operator)|비교 하 여 `accelerator` 반환 하 고 개체와 다른 `true` 않으면는 동일 합니다; 그렇지 않으면 반환 `false`합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[accelerator:: cpu_accelerator 데이터 멤버](#accelerator__cpu_accelerator_data_member)|CPU에 대 한 문자열 상수를 가져옵니다 `accelerator`합니다.|  
|[accelerator:: dedicated_memory 데이터 멤버](#accelerator__dedicated_memory_data_member)|에 대 한 전용된 된 메모리를 가져옵니다는 `accelerator`, (킬로바이트)에서입니다.|  
|[accelerator:: default_accelerator 데이터 멤버](#accelerator__default_accelerator_data_member)|기본값에는 문자열 상수를 가져옵니다 `accelerator`합니다.|  
|[accelerator:: default_cpu_access_type 데이터 멤버](#accelerator__default_cpu_access_type_data_member)|기본 CPU를 가져오거나 설정 합니다. [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 배열 및이 만든 암시적 메모리 할당에 `accelerator`합니다.|  
|[accelerator:: default_view 데이터 멤버](#accelerator__default_view_data_member)|기본 가져옵니다 `accelerator_view` 연관 된 개체는 `accelerator`합니다.|  
|[accelerator:: description 데이터 멤버](#accelerator__description_data_member)|에 대 한 간단한 설명을 가져옵니다는 `accelerator` 장치입니다.|  
|[accelerator:: device_path 데이터 멤버](#accelerator__device_path_data_member)|장치 경로 가져옵니다.|  
|[accelerator:: direct3d_ref 데이터 멤버](#accelerator__direct3d_ref_data_member)|Direct3D 참조에 대 한 문자열 상수를 가져옵니다 `accelerator`합니다.|  
|[accelerator:: direct3d_warp 데이터 멤버](#accelerator__direct3d_warp_data_member)|문자열에 대 한 상수를 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) SSE 스트리밍 SIMD 확장 ()를 사용 하는 다중 코어 Cpu에서 c + + AMP 실행에 사용할 수 있는 개체입니다.|  
|[accelerator:: has_display 데이터 멤버](#accelerator__has_display_data_member)|나타내는 부울 값을 가져옵니다 여부는 `accelerator` 디스플레이에 연결 됩니다.|  
|[accelerator:: is_debug 데이터 멤버](#accelerator__is_debug_data_member)|나타냅니다 여부는 `accelerator` 에 디버그 레이어가 확장 오류 보고에 대 한 활성화 합니다.|  
|[accelerator:: is_emulated 데이터 멤버](#accelerator__is_emulated_data_member)|나타냅니다 여부는 `accelerator` 에뮬레이트됩니다.|  
|[accelerator:: supports_cpu_shared_memory 데이터 멤버](#accelerator__supports_cpu_shared_memory_data_member)|나타냅니다 여부는 `accelerator` 공유 메모리를 지원 합니다.|  
|[accelerator:: supports_double_precision 데이터 멤버](#accelerator__supports_double_precision_data_member)|액셀러레이터가 이중 정밀도 수치를 지원 하는지 여부를 나타냅니다.|  
|[accelerator:: supports_limited_double_precision 데이터 멤버](#accelerator__supports_limited_double_precision_data_member)|액셀러레이터는 제한적으로 이중 정밀도 수치를 지원 하는지 여부를 나타냅니다.|  
|[accelerator:: version 데이터 멤버](#accelerator__version_data_member)|버전을 가져옵니다는 `accelerator`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `accelerator`  
  
## <a name="remarks"></a>설명  
 액셀러레이터 키에는 데이터 병렬 컴퓨팅을 위한 최적화 된 하드웨어 기능입니다. 액셀러레이터 불연속 GPU가 쉽지만 WARP (CPU 쪽 장치 SSE 명령을 사용 하 여 가속화), 또는 자체 CPU DirectX REF 장치와 같은 가상 호스트 측 엔터티입니다 일 수도 있습니다.  
  
 생성할 수는 `accelerator` 기본 장치, 참조 장치 또는 WARP 장치 또는 사용 가능한 장치를 열거 하 여 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameacceleratordtoracceleratordestructora-acceleratoraccelerator-destructor"></a><a name="accelerator___dtoraccelerator_destructor"></a>  accelerator:: ~ accelerator 소멸자  
 소멸은 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 개체입니다.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-nameacceleratoracceleratorconstructora-acceleratoraccelerator-constructor"></a><a name="accelerator__accelerator_constructor"></a>  accelerator:: accelerator 생성자  
 새 인스턴스를 초기화는 [엑셀 러 레이 터 클래스](../../../parallel/amp/reference/accelerator-class.md)합니다.  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Device_path`  
 물리적 장치와의 경로입니다.  
  
 `_Other`  
 복사할 가속기를 지정 합니다.  
  
##  <a name="a-nameacceleratorcpuacceleratordatamembera-acceleratorcpuaccelerator-data-member"></a><a name="accelerator__cpu_accelerator_data_member"></a>  accelerator:: cpu_accelerator 데이터 멤버  
 CPU 엑셀러레이터에 대한 문자열 상수를 가져옵니다.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-nameacceleratorcreateviewmethoda-acceleratorcreateview-method"></a><a name="accelerator__create_view_method"></a>  accelerator:: create_view 메서드  
 지정된 큐 모드를 사용하여 이 액셀러레이터에서 `accelerator_view` 개체를 만들고 반환합니다. 큐 모드가 지정 하지 않으면, 새 `accelerator_view` 사용 하는 [queuing_mode:: immediate](../Topic/concurrency%20namespace%20enums.md#queuing_mode) 큐 모드입니다.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>매개 변수  
 `qmode`  
 큐 모드입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 큐 모드를 사용하는 이 액셀러레이터의 새로운 `accelerator_view` 개체입니다.  
  
##  <a name="a-nameacceleratordedicatedmemorydatamembera-acceleratordedicatedmemory-data-member"></a><a name="accelerator__dedicated_memory_data_member"></a>  accelerator:: dedicated_memory 데이터 멤버  
 에 대 한 전용된 된 메모리를 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md), (킬로바이트)에서입니다.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-nameacceleratordefaultacceleratordatamembera-acceleratordefaultaccelerator-data-member"></a><a name="accelerator__default_accelerator_data_member"></a>  accelerator:: default_accelerator 데이터 멤버  
 기본값에는 문자열 상수를 가져옵니다 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md)합니다.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-nameacceleratordefaultcpuaccesstypedatamembera-acceleratordefaultcpuaccesstype-data-member"></a><a name="accelerator__default_cpu_access_type_data_member"></a>  accelerator:: default_cpu_access_type 데이터 멤버  
 기본 cpu [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) 배열 및이이 만든 암시적 메모리 할당에 `accelerator`합니다.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-nameacceleratordefaultviewdatamembera-acceleratordefaultview-data-member"></a><a name="accelerator__default_view_data_member"></a>  accelerator:: default_view 데이터 멤버  
 연결 된 기본 엑셀 러 레이 터 보기를 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md)합니다.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-nameacceleratordescriptiondatamembera-acceleratordescription-data-member"></a><a name="accelerator__description_data_member"></a>  accelerator:: description 데이터 멤버  
 에 대 한 간단한 설명을 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 장치입니다.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-nameacceleratordevicepathdatamembera-acceleratordevicepath-data-member"></a><a name="accelerator__device_path_data_member"></a>  accelerator:: device_path 데이터 멤버  
 액셀러레이터의 경로를 가져옵니다. 이 경로는 시스템에서 고유합니다.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-nameacceleratordirect3drefdatamembera-acceleratordirect3dref-data-member"></a><a name="accelerator__direct3d_ref_data_member"></a>  accelerator:: direct3d_ref 데이터 멤버  
 Direct3D 참조 엑셀러레이터에 대한 문자열 상수를 가져옵니다.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-nameacceleratordirect3dwarpdatamembera-acceleratordirect3dwarp-data-member"></a><a name="accelerator__direct3d_warp_data_member"></a>  accelerator:: direct3d_warp 데이터 멤버  
 문자열에 대 한 상수를 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) SSE 스트리밍 SIMD 확장 ()를 사용 하 여 다중 코어 Cpu에서 c + + AMP 코드를 실행 하는 데 사용할 수 있는 개체입니다.  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-nameacceleratorgetallmethoda-acceleratorgetall-method"></a><a name="accelerator__get_all_method"></a>  accelerator:: get_all 메서드  
 벡터를 반환 `accelerator` 사용 가능한 모든 액셀러레이터를 나타내는 개체입니다.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>반환 값  
 사용할 수 있는 액셀러레이터의 벡터  
  
##  <a name="a-nameacceleratorgetautoselectionviewmethoda-acceleratorgetautoselectionview-method"></a><a name="accelerator__get_auto_selection_view_method"></a>  accelerator:: get_auto_selection_view 메서드  
 자동 선택 accelerator_view 반환 되는 런타임에 의해 자동으로 선택 될 parallel_for_each 커널을 실행 하기 위한 대상 accelerator_view parallel_for_each 대상 결과 사용 하 여로 지정 합니다. 다른 모든 용도 대 한이 메서드에서 반환 된 accelerator_view가 같습니다는 기본 액셀러레이터의 기본 accelerator_view  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>반환 값  
 자동 선택 accelerator_view 합니다.  
  
##  <a name="a-nameacceleratorgetdedicatedmemorymethoda-acceleratorgetdedicatedmemory-method"></a><a name="accelerator__get_dedicated_memory_method"></a>  accelerator:: get_dedicated_memory 메서드  
 반환에 대 한 전용된 된 메모리는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md), (킬로바이트)에서입니다.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator`를 위해 전용된 메모리(킬로바이트)입니다.  
  
##  <a name="a-nameacceleratorgetdefaultcpuaccesstypemethoda-acceleratorgetdefaultcpuaccesstype-method"></a><a name="accelerator__get_default_cpu_access_type_method"></a>  accelerator:: get_default_cpu_access_type 메서드  
 이 액셀러레이터에서 생성 하는 버퍼에 대 한 기본 cpu access_type를 가져옵니다.  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 이 액셀러레이터에서 생성 하는 버퍼에 대 한 기본 cpu access_type 합니다.  
  
##  <a name="a-nameacceleratorgetdefaultviewmethoda-acceleratorgetdefaultview-method"></a><a name="accelerator__get_default_view_method"></a>  accelerator:: get_default_view 메서드  
 기본 반환 `accelerator_view` 연관 된 개체는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md)합니다.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator_view`와 연결된 기본 `accelerator` 개체입니다.  
  
##  <a name="a-nameacceleratorgetdescriptionmethoda-acceleratorgetdescription-method"></a><a name="accelerator__get_description_method"></a>  accelerator:: get_description 메서드  
 에 대 한 간단한 설명을 반환는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 장치입니다.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator` 장치에 대한 간단한 설명입니다.  
  
##  <a name="a-nameacceleratorgetdevicepathmethoda-acceleratorgetdevicepath-method"></a><a name="accelerator__get_device_path_method"></a>  accelerator:: get_device_path 메서드  
 액셀러레이터의 경로 반환합니다. 이 경로는 시스템에서 고유합니다.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 시스템 차원의 고유한 장치 인스턴스 경로입니다.  
  
##  <a name="a-nameacceleratorgethasdisplaymethoda-acceleratorgethasdisplay-method"></a><a name="accelerator__get_has_display_method"></a>  accelerator:: get_has_display 메서드  
 나타내는 부울 값을 반환 여부는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 표시에 출력할 수 있습니다.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 하는 경우는 `accelerator` 디스플레이;에 출력할 수 그렇지 `false`합니다.  
  
##  <a name="a-nameacceleratorgetisdebugmethoda-acceleratorgetisdebug-method"></a><a name="accelerator__get_is_debug_method"></a>  accelerator:: get_is_debug 메서드  
 결정 여부는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 에 디버그 레이어가 확장 오류 보고에 대 한 활성화 합니다.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 하는 경우는 `accelerator` 에 DEBUG 레이어가 확장 오류 보고에 사용할 수 있습니다. 그렇지 않으면 `false`입니다.  
  
##  <a name="a-nameacceleratorgetisemulatedmethoda-acceleratorgetisemulated-method"></a><a name="accelerator__get_is_emulated_method"></a>  accelerator:: get_is_emulated 메서드  
 확인 여부는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 에뮬레이트됩니다.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 하는 경우는 `accelerator` 에뮬레이트됩니다. 그렇지 않으면 `false`입니다.  
  
##  <a name="a-nameacceleratorgetsupportscpusharedmemorymethoda-acceleratorgetsupportscpusharedmemory-method"></a><a name="accelerator__get_supports_cpu_shared_memory_method"></a>  accelerator:: get_supports_cpu_shared_memory 메서드  
 가속기 가속기와 CPU에서 모두 액세스할 수 있는 메모리를 지원 하는지 여부를 나타내는 부울 값을 반환 합니다.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 액셀러레이터 키 CPU 공유 메모리를 지 원하는 경우 그렇지 않으면 `false`합니다.  
  
##  <a name="a-nameacceleratorgetsupportsdoubleprecisionmethoda-acceleratorgetsupportsdoubleprecision-method"></a><a name="accelerator__get_supports_double_precision_method"></a>  accelerator:: get_supports_double_precision 메서드  
 액셀러레이터가 이중 정밀도 수치를 지원 하는지 여부를 포함 하 여 fused 여부를 나타내는 부울 값을 곱하기 반환 추가 FMA (), 나누기, 역 수 및 사이의 캐스팅 `int` 및 `double`합니다.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 액셀러레이터가 이중 정밀도 수치; 지원 되는 경우 그렇지 않으면 `false`합니다.  
  
##  <a name="a-nameacceleratorgetsupportslimiteddoubleprecisionmethoda-acceleratorgetsupportslimiteddoubleprecision-method"></a><a name="accelerator__get_supports_limited_double_precision_method"></a>  accelerator:: get_supports_limited_double_precision 메서드  
 액셀러레이터가 이중 정밀도 수치를 제한적으로 지원하는지 여부를 나타내는 부울 값을 반환합니다. 액셀러레이터에서 제한적으로만 지원하는 경우 FMA(Fused Multiply Add), 나누기, 역수 및 `int` 및 `double` 사이의 캐스팅은 지원되지 않습니다.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 엑셀러레이터가 이중 정밀도 수치를 제한적으로 지원하는 경우 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="a-nameacceleratorgetversionmethoda-acceleratorgetversion-method"></a><a name="accelerator__get_version_method"></a>  accelerator:: get_version 메서드  
 버전을 반환 된 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md)합니다.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 버전은 `accelerator`합니다.  
  
##  <a name="a-nameacceleratorhasdisplaydatamembera-acceleratorhasdisplay-data-member"></a><a name="accelerator__has_display_data_member"></a>  accelerator:: has_display 데이터 멤버  
 나타내는 부울 값을 가져옵니다 여부는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 표시에 출력할 수 있습니다.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameacceleratorisdebugdatamembera-acceleratorisdebug-data-member"></a><a name="accelerator__is_debug_data_member"></a>  accelerator:: is_debug 데이터 멤버  
 나타내는 부울 값을 가져옵니다 여부는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 에 디버그 레이어가 확장 오류 보고에 대 한 활성화 합니다.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorisemulateddatamembera-acceleratorisemulated-data-member"></a><a name="accelerator__is_emulated_data_member"></a>  accelerator:: is_emulated 데이터 멤버  
 나타내는 부울 값을 가져옵니다 여부는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 에뮬레이트됩니다.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameacceleratoroperatorneqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_neq_operator"></a>  accelerator:: operator! = 연산자  
 비교 하 여 `accelerator` 반환 하 고 개체와 다른 `false` 않으면는 동일 합니다; 그렇지 않으면 반환 `true`합니다.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 이것과 비교할 `accelerator` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `false` 하는 경우 두 `accelerator` 개체가 동일한 지 고, 그렇지 않으면 `true`합니다.  
  
##  <a name="a-nameacceleratoroperatoreqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_operator"></a>  accelerator:: operator = 연산자  
 지정 된 내용을 복사 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 여기에 개체입니다.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
  `accelerator` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `accelerator` 개체입니다.  
  
##  <a name="a-nameacceleratoroperatoreqeqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_eq_operator"></a>  accelerator:: operator = = 연산자  
 비교 하 여 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 반환 하 고 개체와 다른 `true` 않으면는 동일 합니다; 그렇지 않으면 반환 `false`합니다.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 이것과 비교할 `accelerator` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 하는 경우 다른 `accelerator` 개체는이 같은 `accelerator` 그렇지 그렇지 `false`합니다.  
  
##  <a name="a-nameacceleratorsetdefaultmethoda-acceleratorsetdefault-method"></a><a name="accelerator__set_default_method"></a>  accelerator:: set_default 메서드  
 암시적으로 기본 액셀러레이터를 사용 하는 모든 작업에 사용할 기본 액셀러레이터를 설정 합니다. 이 메서드는 런타임 선택한 기본 액셀러레이터 이미 암시적으로 기본 액셀러레이터를 사용 하는 작업에 사용 되지 않은 경우에 성공  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Path`  
 액셀러레이터의 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 기본 액셀러레이터 설정 호출이 성공 하면 됩니다. 그렇지 않으면 `false`입니다.  
  
##  <a name="a-nameacceleratorsetdefaultcpuaccesstypemethoda-acceleratorsetdefaultcpuaccesstype-method"></a><a name="accelerator__set_default_cpu_access_type_method"></a>  accelerator:: set_default_cpu_access_type 메서드  
 이 액세스 array_views의 일부는이 액셀러레이터가이 액셀러레이터에서 또는 암시적 메모리 할당에 대 한 만든 배열에 대 한 기본 cpu access_type를 설정 합니다. 이 메서드는이 엑셀 러 레이이 터에 대 한 런타임 선택한 default_cpu_access_type 사용 되지 않은 아직이 액셀러레이터에서 액세스 하는 array_view를 백업 하는 암시적 메모리 할당 또는 배열 할당에 대 한 가속기 default_cpu_access_type가 아직이 메서드에 대 한 이전 호출에서 재정의 된 경우에 성공 합니다.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Default_cpu_access_type`  
 이 액셀러레이터에서 배열/array_view 메모리 할당에 사용할 기본 cpu access_type 합니다.  
  
### <a name="return-value"></a>반환 값  
 액셀러레이터 키에 대 한 기본 cpu access_type 성공적으로 설정 된 경우를 나타내는 부울 값.  
  
##  <a name="a-nameacceleratorsupportscpusharedmemorydatamembera-acceleratorsupportscpusharedmemory-data-member"></a><a name="accelerator__supports_cpu_shared_memory_data_member"></a>  accelerator:: supports_cpu_shared_memory 데이터 멤버  
 나타내는 부울 값을 가져옵니다 여부는 `accelerator` 공유 메모리를 지원 합니다.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-nameacceleratorsupportsdoubleprecisiondatamembera-acceleratorsupportsdoubleprecision-data-member"></a><a name="accelerator__supports_double_precision_data_member"></a>  accelerator:: supports_double_precision 데이터 멤버  
 액셀러레이터가 배정밀도 수치를 지원하는지 여부를 나타내는 부울 값을 가져옵니다.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-nameacceleratorsupportslimiteddoubleprecisiondatamembera-acceleratorsupportslimiteddoubleprecision-data-member"></a><a name="accelerator__supports_limited_double_precision_data_member"></a>  accelerator:: supports_limited_double_precision 데이터 멤버  
 액셀러레이터 키 이중 정밀도 수치에 대 한 지원이 제한적으로 하는지 여부를 나타내는 부울 값을 가져옵니다. 액셀러레이터에서 제한적으로만 지원하는 경우 FMA(Fused Multiply Add), 나누기, 역수 및 `int` 및 `double` 사이의 캐스팅은 지원되지 않습니다.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameacceleratorversiondatamembera-acceleratorversion-data-member"></a><a name="accelerator__version_data_member"></a>  accelerator:: version 데이터 멤버  
 버전을 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md)합니다.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewdtoracceleratorviewdestructora-acceleratorviewacceleratorview-destructor"></a><a name="accelerator_view___dtoraccelerator_view_destructor"></a>  accelerator_view:: ~ accelerator_view 소멸자  
 소멸은 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체입니다.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="a-nameacceleratorviewacceleratordatamembera-acceleratorviewaccelerator-data-member"></a><a name="accelerator_view__accelerator_data_member"></a>  accelerator_view:: accelerator 데이터 멤버  
 가져옵니다는 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 개체에 대 한는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체입니다.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-nameacceleratorviewacceleratorviewconstructora-acceleratorviewacceleratorview-constructor"></a><a name="accelerator_view__accelerator_view_constructor"></a>  accelerator_view:: accelerator_view 생성자  
 새 인스턴스를 초기화는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 클래스는 기존 복사 하 여 `accelerator_view` 개체입니다.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
  `accelerator_view` 복사할 개체입니다.  
  
##  <a name="a-nameacceleratorviewcreatemarkermethoda-acceleratorviewcreatemarker-method"></a><a name="accelerator_view__create_marker_method"></a>  accelerator_view:: create_marker 메서드  
 지금까지이 제출 된 모든 명령이 완료를 추적 하는 미래 반환 `accelerator_view` 개체입니다.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>반환 값  
 지금까지이 제출 된 모든 명령이 완료를 추적 하는 미래 `accelerator_view` 개체입니다.  
  
##  <a name="a-nameacceleratorviewflushmethoda-acceleratorviewflush-method"></a><a name="accelerator_view__flush_method"></a>  accelerator_view:: flush 메서드  
 모든 보류 중인 명령은 큐에 대기 중인 전송에서 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 실행을 위한 엑셀 러 레이 터에는 개체입니다.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>반환 값  
 `void`를 반환합니다.  
  
##  <a name="a-nameacceleratorviewgetacceleratormethoda-acceleratorviewgetaccelerator-method"></a><a name="accelerator_view__get_accelerator_method"></a>  accelerator_view:: get_accelerator 메서드  
 반환 된 [엑셀 러 레이 터](../../../parallel/amp/reference/accelerator-class.md) 개체에 대 한는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체입니다.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>반환 값  
  `accelerator` 개체에 대 한는 `accelerator_view` 개체입니다.  
  
##  <a name="a-nameacceleratorviewgetisautoselectionmethoda-acceleratorviewgetisautoselection-method"></a><a name="accelerator_view__get_is_auto_selection_method"></a>  accelerator_view:: get_is_auto_selection 메서드  
 여부를 런타임에서 자동으로 선택 됩니다 적절 한 가속기는 accelerator_view로 전달 될 때를 나타내는 부울 값을 반환 된 [parallel_for_each](../Topic/concurrency%20namespace%20functions.md#parallel_for_each)합니다.  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `true` 런타임에서 적절 한 가속기; 자동으로 선택 하는 경우 그렇지 않으면 `false`합니다.  
  
##  <a name="a-nameacceleratorviewgetisdebugmethoda-acceleratorviewgetisdebug-method"></a><a name="accelerator_view__get_is_debug_method"></a>  accelerator_view:: get_is_debug 메서드  
 나타내는 부울 값을 반환 여부는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체에 DEBUG 레이어가 확장 오류 보고에 대 한 활성화 합니다.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값입니다.  
  
##  <a name="a-nameacceleratorviewgetqueuingmodemethoda-acceleratorviewgetqueuingmode-method"></a><a name="accelerator_view__get_queuing_mode_method"></a>  accelerator_view:: get_queuing_mode 메서드  
 큐 모드를 반환 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체입니다.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `accelerator_view` 개체의 큐 모드입니다.  
  
##  <a name="a-nameacceleratorviewgetversionmethoda-acceleratorviewgetversion-method"></a><a name="accelerator_view__get_version_method"></a>  accelerator_view:: get_version 메서드  
 버전을 반환 된 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md)합니다.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 버전은 `accelerator_view`합니다.  
  
##  <a name="a-nameacceleratorviewisautoselectiondatamembera-acceleratorviewisautoselection-data-member"></a><a name="accelerator_view__is_auto_selection_data_member"></a>  accelerator_view:: is_auto_selection 데이터 멤버  
 여부를 런타임에서 자동으로 선택 됩니다 적절 한 가속기는 accelerator_view로 전달 될 때를 나타내는 부울 값을 가져옵니다는 [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each)합니다.  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameacceleratorviewisdebugdatamembera-acceleratorviewisdebug-data-member"></a><a name="accelerator_view__is_debug_data_member"></a>  accelerator_view:: is_debug 데이터 멤버  
 나타내는 부울 값을 가져옵니다 여부는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체에 DEBUG 레이어가 확장 오류 보고에 대 한 활성화 합니다.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorviewoperatorneqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_neq_operator"></a>  accelerator_view:: operator! = 연산자  
 비교 하 여 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 반환 하 고 개체와 다른 `false` 않으면는 동일 합니다; 그렇지 않으면 반환 `true`합니다.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 이것과 비교할 `accelerator_view` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개체가 같으면 `false`이고, 그렇지 않으면 `true`입니다.  
  
##  <a name="a-nameacceleratorviewoperatoreqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_operator"></a>  accelerator_view:: operator = 연산자  
 지정 된 내용을 복사 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 을 여기에 개체입니다.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
  `accelerator_view` 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 수정된 `accelerator_view` 개체에 대한 참조입니다.  
  
##  <a name="a-nameacceleratorviewoperatoreqeqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_eq_operator"></a>  accelerator_view:: operator = = 연산자  
 비교 하 여 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 반환 하 고 개체와 다른 `true` 않으면는 동일 합니다; 그렇지 않으면 반환 `false`합니다.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 이것과 비교할 `accelerator_view` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개체가 같으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="a-nameacceleratorviewqueuingmodedatamembera-acceleratorviewqueuingmode-data-member"></a><a name="accelerator_view__queuing_mode_data_member"></a>  accelerator_view:: queuing_mode 데이터 멤버  
 큐 모드를 가져옵니다는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체입니다.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameacceleratorviewversiondatamembera-acceleratorviewversion-data-member"></a><a name="accelerator_view__version_data_member"></a>  accelerator_view:: version 데이터 멤버  
 버전을 가져옵니다는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md)합니다.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewwaitmethoda-acceleratorviewwait-method"></a><a name="accelerator_view__wait_method"></a>  accelerator_view:: wait 메서드  
 제출 된 모든 명령이 대기는 [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) 완료 하는 개체입니다.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>반환 값  
 `void`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 네임 스페이스 (c + + AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
