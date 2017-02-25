---
title: "Concurrency::direct3d 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::direct3d"
  - "amprt/Concurrency::direct3d"
  - "amp_short_vectors/Concurrency::direct3d"
  - "amp_graphics/Concurrency::direct3d"
  - "amp_math/Concurrency::direct3d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "direct3d 네임스페이스"
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Concurrency::direct3d 네임스페이스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`direct3d` 네임스페이스가 D3D 상호 운용성을 지원하는 기능을 제공합니다.  중복된 임시 사본을 만들지 않고도 AMP 코드에서 계산을 위해 D3D 리소스를 완벽하게 사용할 뿐만 아니라 D3D 코드의 AMP에서 만든 리소스를 사용할 수 있습니다.  C\+\+ AMP를 사용하여 DirectX 응용 프로그램의 계산 집중적인 부분을 점차적으로 가속화하고, AMP 계산에서 생성된 데이터에 D3D API를 사용할 수 있습니다.  
  
## 구문  
  
```  
namespace direct3d;  
```  
  
## 멤버  
  
### 클래스  
  
|Name|설명|  
|----------|--------|  
|[scoped\_d3d\_access\_lock 클래스](../../../parallel/amp/reference/scoped-d3d-access-lock-class.md)|`accelerator_view` 개체의 D3D 액세스 잠금에 대한 RAII 래퍼입니다.|  
  
### 구조체  
  
|Name|설명|  
|----------|--------|  
|[adopt\_d3d\_access\_lock\_t 구조체](../../../parallel/amp/reference/adopt-d3d-access-lock-t-structure.md)|D3D 액세스 잠금을 획득하지 사용해야 함을 나타내는 태그 형식입니다.|  
  
### 함수  
  
|Name|설명|  
|----------|--------|  
|[abs 함수](../Topic/abs%20Function.md)|인수의 절대 값을 반환합니다.|  
|[clamp 함수](../Topic/clamp%20Function.md)|오버로드됨.  \_X를 지정된 \_Min 및 \_Max 범위로 제한|  
|[countbits 함수](../Topic/countbits%20Function.md)|\_X에서 설정 비트의 수 계산|  
|[create\_accelerator\_view 함수](../Topic/create_accelerator_view%20Function.md)|포인터에서 Direct3D 장치 인터페이스까지 [accelerator\_view 클래스](../../../parallel/amp/reference/accelerator-view-class.md)를 만듭니다.|  
|[d3d\_access\_lock 함수](../Topic/d3d_access_lock%20Function.md)|accelerator\_view와 공유되는 리소스에서 D3D 작업을 안전하게 수행할 목적으로 accelerator\_view에 대한 잠금을 획득합니다.|  
|[d3d\_access\_try\_lock 함수](../Topic/d3d_access_try_lock%20Function.md)|차단하지 않고 액셀러레이터 보기에 D3D 액세스 잠금을 얻으려고 시도합니다.|  
|[d3d\_access\_unlock 함수](../Topic/d3d_access_unlock%20Function.md)|제공된 accelerator\_view에 대한 D3D 액세스 잠금을 릴리스합니다.|  
|[firstbithigh 함수](../Topic/firstbithigh%20Function.md)|가장 높은 순위의 비트에서 시작하여 아래쪽으로 작업하여 \_X에서 첫 번째 설정 비트의 위치를 가져옵니다.|  
|[firstbitlow 함수](../Topic/firstbitlow%20Function.md)|가장 낮은 순위의 비트에서 시작하여 위쪽으로 작업하여 \_X에서 첫 번째 설정 비트의 위치를 가져옵니다.|  
|[get\_buffer 함수](../Topic/get_buffer%20Function.md)|배열 내부 D3D 버퍼 인터페이스를 가져옵니다.|  
|[imax 함수](../Topic/imax%20Function.md)|두 개의 값을 비교하여 더 큰 값을 반환합니다.|  
|[imin 함수](../Topic/imin%20Function.md)|두 개의 값을 비교하여 더 작은 값을 반환합니다.|  
|[is\_timeout\_disabled 함수](../Topic/is_timeout_disabled%20Function.md)|지정된 accelerator\_view에 대해 제한 시간이 비활성화되었는지 여부를 나타내는 부울 플래그를 반환합니다.|  
|[mad 함수](../Topic/mad%20Function.md)|오버로드됨.  세 인수로 산술 곱하기\/더하기 작업 수행: \_X \* \_Y \+ \_Z|  
|[make\_array 함수](../Topic/make_array%20Function.md)|D3D 버퍼 인터페이스 포인터에서 배열을 만듭니다.|  
|[noise 함수](../Topic/noise%20Function.md)|Perlin 노이즈 알고리즘을 사용하여 임의의 값을 생성합니다.|  
|[radians 함수](../Topic/radians%20Function.md)|\_X를 각도에서 라디안으로 변환합니다.|  
|[rcp 함수](../Topic/rcp%20Function.md)|인수의 역수를 빠르고 대략적으로 계산합니다.|  
|[reversebits 함수](../Topic/reversebits%20Function.md)|\_X의 비트 순서를 반대로 바꿉니다.|  
|[saturate 함수](../Topic/saturate%20Function.md)|\_X를 0 \- 1의 범위 내로 제한|  
|[sign 함수](../Topic/sign%20Function.md)|오버로드됨.  인수의 기호를 반환합니다.|  
|[smoothstep 함수](../Topic/smoothstep%20Function.md)|\_X가 \[\_Min, \_Max\]의 범위 내에 있는 경우, 0과 1 사이의 부드러운 Hermite 보간을 반환합니다.|  
|[step 함수](../Topic/step%20Function.md)|두 개의 값을 비교하여 더 큰 값에 기반한 0 또는 1을 반환합니다.|  
|[umax 함수](../Topic/umax%20Function.md)|서명되지 않은 두 개의 값을 비교하여 더 큰 값을 반환합니다.|  
|[umin 함수](../Topic/umin%20Function.md)|서명되지 않은 두 개의 값을 비교하여 더 작은 값을 반환합니다.|  
  
## 요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)