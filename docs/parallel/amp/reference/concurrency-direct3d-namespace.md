---
title: "Concurrency:: direct3d Namespace | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
dev_langs:
- C++
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 94e0542910484166a01bd79beb9dfaa805aae6cd
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d 네임스페이스
`direct3d` 네임 스페이스 D3D 상호 운용성을 지 원하는 기능을 제공 합니다. 그 AMP 코드에 대 한 계산을 위해 D3D 리소스를 원활 하 게 사용 하도록 설정 뿐만 아니라 중간 중복 복사본을 만들지 않고 amp에서 D3D 코드에서 만든 리소스를 사용할 수 있습니다. C + + AMP를 사용 하 여 DirectX 응용 프로그램의 계산 집약적인 섹션을 가속화 하 고 D3D API를 사용 하 여 AMP 계산에서 생성 된 데이터에 증분 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="classes"></a>클래스  
  
|이름|설명|  
|----------|-----------------|  
|[scoped_d3d_access_lock 클래스](scoped-d3d-access-lock-class.md)|D3D 액세스 잠금에 대 한 RAII 래퍼는 `accelerator_view` 개체입니다.|  
  
### <a name="structures"></a>구조체  
  
|이름|설명|  
|----------|-----------------|  
|[adopt_d3d_access_lock_t 구조체](adopt-d3d-access-lock-t-structure.md)|D3D 액세스 잠금을 나타내기 위해 태그 형식은 채택 되지 않고 됩니다 획득 합니다.|  
  
### <a name="functions"></a>함수  
  
|이름|설명|  
|----------|-----------------|  
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|인수의 절대값을 반환합니다.|  
|[clamp](concurrency-direct3d-namespace-functions-amp.md#clamp)|오버로드됨. 지정 된 _Min 및 _Max 범위 _X 고정|  
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|_X의 비트를 집합의 개수|  
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|만들고 있는 [accelerator_view 클래스](accelerator-view-class.md) Direct3D 장치 인터페이스에 대 한 포인터에서|  
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|안전 하 게는 accelerator_view와 공유 리소스에 대 한 D3D 작업을 수행할 목적으로 accelerator_view에 잠금을 획득합니다|  
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|차단 하지 않고는 accelerator_view D3D 액세스 잠금을 획득 하려고 시도 합니다.|  
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|주어진된 accelerator_view에 D3D 액세스 잠금을 해제 합니다.|  
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|_X의 가장 높은 비트가에서 시작 하 고 아래쪽으로 작업의 첫 번째 설정 비트의 위치를 가져옵니다.|  
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|_X의 최하위 비트가에서 시작 하 고 위쪽으로 작업의 첫 번째 설정 비트의 위치를 가져옵니다.|  
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|기본 배열 D3D 버퍼 인터페이스를 가져옵니다.|  
|[imax](concurrency-direct3d-namespace-functions-amp.md#imax)|큰 값을 반환 하는 두 값을 비교 합니다.|  
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|작은 값을 반환 하는 두 값을 비교 합니다.|  
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|시간 제한 지정된 accelerator_view를 사용할 경우를 나타내는 부울 플래그를 반환 합니다.|  
|[mad](concurrency-direct3d-namespace-functions-amp.md#mad)|오버로드됨. 세 개의 인수에 대 한 산술 곱하기/추가 작업 수행: _X * _Y + _Z|  
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|D3D 버퍼 인터페이스 포인터에서 배열을 만듭니다.|  
|[노이즈](concurrency-direct3d-namespace-functions-amp.md#noise)|Perlin 노이즈 알고리즘을 사용 하 여 임의의 값을 생성 합니다.|  
|[라디안](concurrency-direct3d-namespace-functions-amp.md#radians)|_X 각도에서 라디안으로 변환|  
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|인수의 신속 하 고 대략적인 역을 계산합니다.|  
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|_X의 비트의 순서를 반대로 바꿉니다.|  
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|0 또는 1의 범위 내 _X 고정|  
|[로그인](concurrency-direct3d-namespace-functions-amp.md#sign)|오버로드됨. 인수의 부호를 반환 합니다.|  
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|_X가 [_Min, _Max] 범위에 경우에 0과 1 사이의 부드러운 Hermite 보간을 반환 합니다.|  
|[단계](concurrency-direct3d-namespace-functions-amp.md#step)|두 값을 반환 하는 0 또는 1을 기반으로 어떤 값이 큰 비교|  
|[umax](concurrency-direct3d-namespace-functions-amp.md#umax)|큰 값을 반환 하는 두 개의 부호 없는 값을 비교 합니다.|  
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|작은 값을 반환 하는 두 개의 부호 없는 값을 비교 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)

