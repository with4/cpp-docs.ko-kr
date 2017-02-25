---
title: "texture 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::texture"
dev_langs: 
  - "C++"
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# texture 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

텍스처는 범위 도메인에서 `accelerator_view`에 대한 데이터 집계입니다.  범위 도메인에 있는 각 요소에 대한 변수의 컬렉션입니다.  각 변수는 C\+\+ 기본 형식\(`unsigned int`, `int`, `float`, `double`\), 스칼라 형식\(`norm` 또는 `unorm`\) 또는 short 벡터 형식에 해당하는 값을 갖습니다.  
  
## 구문  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture;  
```  
  
#### 매개 변수  
 `_Value_type`  
 질감에 있는 요소의 형식입니다.  
  
 `_Rank`  
 질감의 순위입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`scalar_type`|스칼라 형식.|  
|`value_type`|값 형식.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[texture::texture 생성자](../Topic/texture::texture%20Constructor.md)|[texture](../../../parallel/amp/reference/texture-class.md) 클래스의 새 인스턴스를 초기화합니다.|  
|[texture::~texture 소멸자](../Topic/texture::~texture%20Destructor.md)|[texture](../../../parallel/amp/reference/texture-class.md) 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[texture::copy\_to 메서드](../Topic/texture::copy_to%20Method.md)|[텍스처](../../../parallel/amp/reference/texture-class.md) 개체를 전체 복사를 수행하여 대상에 복사합니다.|  
|[texture::data 메서드](../Topic/texture::data%20Method.md)|이 질감의 원시 데이터에 대한 CPU 포인터를 반환합니다.|  
|[texture::get 메서드](../Topic/texture::get%20Method.md)|지정된 인덱스에 있는 요소의 값을 반환합니다.|  
|[texture::get\_associated\_accelerator\_view 메서드](../Topic/texture::get_associated_accelerator_view%20Method.md)|이 텍스처가 복사되는 기본 대상인 [accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md)를 반환합니다.|  
|[texture::get\_depth\_pitch 메서드](../Topic/texture::get_depth_pitch%20Method.md)|CPU의 3D 스테이징 텍스처에서 각 깊이 조각 사이의 바이트 수를 반환합니다.|  
|[texture::get\_row\_pitch 메서드](../Topic/texture::get_row_pitch%20Method.md)|CPU의 2D 또는 3D 스테이징 텍스처의 각 행 사이의 바이트 수를 반환합니다.|  
|[texture::set 메서드](../Topic/texture::set%20Method.md)|지정된 인덱스에서 요소 값을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[texture::operator\(\) 연산자](../Topic/texture::operator\(\)%20Operator.md)|매개 변수로 지정된 요소 값을 반환합니다.|  
|[texture::operatorOperator](../Topic/texture::operatorOperator.md)|지정된 인덱스에 있는 요소를 반환합니다.|  
|[texture::operator\= 연산자](../Topic/texture::operator=%20Operator.md)|지정된 [텍스처](../../../parallel/amp/reference/texture-class.md) 개체를 여기로 복사합니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[texture::rank 상수](../Topic/texture::rank%20Constant.md)|[텍스처](../../../parallel/amp/reference/texture-class.md) 개체의 차수를 가져옵니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[texture::associated\_accelerator\_view 데이터 멤버](../Topic/texture::associated_accelerator_view%20Data%20Member.md)|이 텍스처가 복사되는 기본 대상인 [accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md)를 가져옵니다.|  
|[texture::depth\_pitch 데이터 멤버](../Topic/texture::depth_pitch%20Data%20Member.md)|CPU의 3D 스테이징 텍스처에서 각 깊이 조각 사이의 바이트 수를 가져옵니다.|  
|[texture::row\_pitch 데이터 멤버](../Topic/texture::row_pitch%20Data%20Member.md)|CPU의 2D 또는 3D 스테이징 텍스처의 각 행 사이의 바이트 수를 가져옵니다.|  
  
## 상속 계층  
 `_Texture_base`  
  
 `texture`  
  
## 요구 사항  
 **헤더:** amp\_graphics.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)