---
title: "Concurrency:: graphics Namespace | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP_GRAPHICS/Concurrency
dev_langs:
- C++
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
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
ms.openlocfilehash: e08a9bc52b7ce519508bb1682287e75070d341a1
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics 네임스페이스
그래픽 네임 스페이스에는 형식 및 그래픽 프로그래밍에 대 한 설계 된 함수를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
namespace graphics;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="namespaces"></a>네임스페이스  
  
|이름|설명|  
|----------|-----------------|  
|[Concurrency::graphics::direct3d 네임스페이스](concurrency-graphics-direct3d-namespace.md)|Direct3D interop에 대 한 기능을 제공합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|이름|설명|  
|----------|-----------------|  
|`uint`|요소 유형을 [uint_2 클래스](uint-2-class.md), [uint_3 클래스](uint-3-class.md), 및 [uint_4 클래스](uint-4-class.md)합니다. 로 정의 된 `typedef unsigned int uint;`합니다.|  
  
### <a name="enumerations"></a>열거형  
  
|이름|설명|  
|----------|-----------------|  
|[address_mode 열거형](concurrency-graphics-namespace-enums.md#address_mode)합니다.|질감 샘플링에 대해 지원 되는 주소 모드를 지정 합니다.|  
|[filter_mode 열거형](concurrency-graphics-namespace-enums.md#filter_mode)|질감 샘플링에 대해 지원 되는 필터 모드를 지정 합니다.|  
  
### <a name="classes"></a>클래스  
  
|이름|설명|  
|----------|-----------------|  
|[texture 클래스](texture-class.md)|질감은 데이터 범위 도메인에는 accelerator_view에 집계 합니다. 익스텐트 도메인에 있는 각 요소에 대 한 변수 모음입니다. C + + 기본 형식 (부호 없는 int, int, float, double)에 해당 하는 값을 보유 하는 각 변수 또는 concurrency:: graphics에 정의 된 스칼라 형식 norm 또는 unorm (concurrency:: graphics에 정의 됨), 또는 적합 short 벡터 형식입니다.|  
|[writeonly_texture_view 클래스](writeonly-texture-view-class.md)|writeonly_texture_view writeonly 질감에 대 한 액세스를 제공합니다.|  
|[double_2 클래스](double-2-class.md)|2의 짧은 벡터 나타냅니다 `double` 값입니다.|  
|[double_3 클래스](double-3-class.md)|3은 짧은 벡터를 나타냅니다 `double` 값입니다.|  
|[double_4 클래스](double-4-class.md)|4의 짧은 벡터 나타냅니다 `double` 값입니다.|  
|[float_2 클래스](float-2-class.md)|2의 짧은 벡터 나타냅니다 `float` 값입니다.|  
|[float_3 클래스](float-3-class.md)|3은 짧은 벡터를 나타냅니다 `float` 값입니다.|  
|[float_4 클래스](float-4-class.md)|4의 짧은 벡터 나타냅니다 `float` 값입니다.|  
|[int_2 클래스](int-2-class.md)|2의 짧은 벡터 나타냅니다 `int` 값입니다.|  
|[int_3 클래스](int-3-class.md)|3은 짧은 벡터를 나타냅니다 `int` 값입니다.|  
|[int_4 클래스](int-4-class.md)|4의 짧은 벡터 나타냅니다 `int` 값입니다.|  
|[norm_2 클래스](norm-2-class.md)|2의 짧은 벡터 나타냅니다 `norm` 값입니다.|  
|[norm_3 클래스](norm-3-class.md)|3은 짧은 벡터를 나타냅니다 `norm` 값입니다.|  
|[norm_4 클래스](norm-4-class.md)|4의 짧은 벡터 나타냅니다 `norm` 값입니다.|  
|[uint_2 클래스](uint-2-class.md)|2의 짧은 벡터 나타냅니다 `uint` 값입니다.|  
|[uint_3 클래스](uint-3-class.md)|3은 짧은 벡터를 나타냅니다 `uint` 값입니다.|  
|[uint_4 클래스](uint-4-class.md)|4의 짧은 벡터 나타냅니다 `uint` 값입니다.|  
|[unorm_2 클래스](unorm-2-class.md)|2의 짧은 벡터 나타냅니다 `unorm` 값입니다.|  
|[unorm_3 클래스](unorm-3-class.md)|3은 짧은 벡터를 나타냅니다 `unorm` 값입니다.|  
|[unorm_4 클래스](unorm-4-class.md)|4의 짧은 벡터 나타냅니다 `unorm` 값입니다.|  
|[sampler 클래스](sampler-class.md)|질감 샘플링에 사용할 샘플러 구성을 나타냅니다.|  
|[short_vector 구조체](short-vector-structure.md)|값의 short 벡터의 기본 구현을 제공합니다.|  
|[short_vector_traits 구조체](short-vector-traits-structure.md)|Short 벡터 형식 및 길이 대 한 검색을 위해 제공합니다.|  
|[texture_view 클래스](texture-view-class.md)|읽기 권한 및 질감에 대 한 쓰기 액세스를 제공합니다.|  
  
### <a name="functions"></a>함수  
  
|이름|설명|  
|----------|-----------------|  
|[copy](concurrency-graphics-namespace-functions.md#copy)|오버로드됨. 원본 질감의 내용을 대상 호스트 버퍼에 복사합니다.|  
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|오버로드됨. 대상 호스트 버퍼에 원본 질감의 콘텐츠를 비동기적으로 복사합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_graphics.h  
  
 **네임스페이스:** 동시성  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)

