---
title: "Concurrency::graphics 네임스페이스 | Microsoft Docs"
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
  - "amp_graphics/Concurrency::graphics"
  - "amp_short_vectors/Concurrency::graphics"
dev_langs: 
  - "C++"
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::graphics 네임스페이스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

그래픽 네임스페이스는 그래픽 프로그래밍을 위해 디자인된 유형 및 기능을 제공합니다.  
  
## 구문  
  
```  
namespace graphics;  
```  
  
## 멤버  
  
### 네임스페이스  
  
|Name|설명|  
|----------|--------|  
|[Concurrency::graphics::direct3d 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md)|Direct3D interop기능을 제공합니다.|  
  
### 형식 정의  
  
|Name|설명|  
|----------|--------|  
|`uint`|[uint\_2 클래스](../../../parallel/amp/reference/uint-2-class.md), [uint\_3 클래스](../../../parallel/amp/reference/uint-3-class.md) 및 [uint\_4 클래스](../../../parallel/amp/reference/uint-4-class.md)에 대한 요소 형식입니다.  `typedef unsigned int uint;`로 정의되었습니다.|  
  
### 열거형  
  
|Name|설명|  
|----------|--------|  
|[address\_mode 열거형](../Topic/address_mode%20Enumeration.md)|질감 샘플링에 지원되는 주소 모드를 지정합니다.|  
|[filter\_mode 열거형](../Topic/filter_mode%20Enumeration.md)|질감 샘플링에 지원되는 필터 모드를 지정합니다.|  
  
### 클래스  
  
|Name|설명|  
|----------|--------|  
|[texture 클래스](../../../parallel/amp/reference/texture-class.md)|텍스처는 범위 도메인에서 accelerator\_view에 대한 데이터 집계입니다.  범위 도메인에 있는 각 요소에 대한 변수의 컬렉션입니다.  각 변수는 C\+\+ 기본 형식\(unsigned int, int, float, double\) 또는 스칼라 형식 norm 또는 unorm\(concurrency::graphics에 정의\) 또는 concurrency::graphics에 정의된 적합한 short 벡터 형식에 해당하는 값을 갖습니다.|  
|[writeonly\_texture\_view 클래스](../../../parallel/amp/reference/writeonly-texture-view-class.md)|writeonly\_texture\_view는 텍스처에 대한 writeonly 액세스를 제공합니다.|  
|[double\_2 클래스](../../../parallel/amp/reference/double-2-class.md)|2 `double` 값의 short 백터를 나타냅니다.|  
|[double\_3 클래스](../../../parallel/amp/reference/double-3-class.md)|3 `double` 값의 short 백터를 나타냅니다.|  
|[double\_4 클래스](../../../parallel/amp/reference/double-4-class.md)|4 `double` 값의 short 백터를 나타냅니다.|  
|[float\_2 클래스](../../../parallel/amp/reference/float-2-class.md)|2 `float` 값의 short 백터를 나타냅니다.|  
|[float\_3 클래스](../../../parallel/amp/reference/float-3-class.md)|3 `float` 값의 short 백터를 나타냅니다.|  
|[float\_4 클래스](../../../parallel/amp/reference/float-4-class.md)|4 `float` 값의 short 백터를 나타냅니다.|  
|[int\_2 클래스](../../../parallel/amp/reference/int-2-class.md)|2 `int` 값의 short 백터를 나타냅니다.|  
|[int\_3 클래스](../../../parallel/amp/reference/int-3-class.md)|3 `int` 값의 short 백터를 나타냅니다.|  
|[int\_4 클래스](../../../parallel/amp/reference/int-4-class.md)|4 `int` 값의 short 백터를 나타냅니다.|  
|[norm\_2 클래스](../../../parallel/amp/reference/norm-2-class.md)|2 `norm` 값의 short 백터를 나타냅니다.|  
|[norm\_3 클래스](../../../parallel/amp/reference/norm-3-class.md)|3 `norm` 값의 short 백터를 나타냅니다.|  
|[norm\_4 클래스](../../../parallel/amp/reference/norm-4-class.md)|4 `norm` 값의 short 백터를 나타냅니다.|  
|[uint\_2 클래스](../../../parallel/amp/reference/uint-2-class.md)|2 `uint` 값의 short 백터를 나타냅니다.|  
|[uint\_3 클래스](../../../parallel/amp/reference/uint-3-class.md)|3 `uint` 값의 short 백터를 나타냅니다.|  
|[uint\_4 클래스](../../../parallel/amp/reference/uint-4-class.md)|4 `uint` 값의 short 백터를 나타냅니다.|  
|[unorm\_2 클래스](../../../parallel/amp/reference/unorm-2-class.md)|2 `unorm` 값의 short 백터를 나타냅니다.|  
|[unorm\_3 클래스](../../../parallel/amp/reference/unorm-3-class.md)|3 `unorm` 값의 short 백터를 나타냅니다.|  
|[unorm\_4 클래스](../../../parallel/amp/reference/unorm-4-class.md)|4 `unorm` 값의 short 백터를 나타냅니다.|  
|[sampler 클래스](../../../parallel/amp/reference/sampler-class.md)|텍스처 샘플링에 사용된 견본 구성을 나타냅니다.|  
|[short\_vector 구조체](../../../parallel/amp/reference/short-vector-structure.md)|짧은 벡터 값의 기본 구현을 제공합니다.|  
|[short\_vector\_traits 구조체](../../../parallel/amp/reference/short-vector-traits-structure.md)|짧은 벡터의 길이와 형식 검색 기능을 제공합니다.|  
|[texture\_view 클래스](../../../parallel/amp/reference/texture-view-class.md)|텍스처에 대한 쓰기 및 읽기 액세스를 제공합니다.|  
  
### 함수  
  
|Name|설명|  
|----------|--------|  
|[copy 함수](../Topic/copy%20Function.md)|오버로드됨.  소스 텍스처의 콘텐츠를 대상 호스트 버퍼로 복사합니다.|  
|[copy\_async 함수](../Topic/copy_async%20Function.md)|오버로드됨.  대상 호스트 버퍼로 소스 텍스처의 내용을 비동기적으로 복사합니다.|  
  
## 요구 사항  
 **헤더:** amp\_graphics.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)