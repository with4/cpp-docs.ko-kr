---
title: "texture_view 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# texture_view 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

텍스처에 대한 쓰기 및 읽기 액세스를 제공합니다.  `texture_view`는 값 형식이 기본 32비트 bpse가 있는 `int`, `unsigned int` 또는 `float`인 질감을 읽는 데만 사용할 수 있습니다.  다른 질감 형식을 알아보려면 `texture_view<const _Value_type, _Rank>`를 사용합니다.  
  
## 구문  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view : public details::_Texture_base<_Value_type, _Rank>;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view<const _Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
```  
  
#### 매개 변수  
 `_Value_type`  
 질감 집계에 있는 요소의 형식입니다.  
  
 `_Rank`  
 `texture_view`의 순위입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`value_type`|질감 집계에 있는 요소의 형식입니다.|  
|`coordinates_type`|`texture_view`의 텍셀을 지정하는 데 사용된 좌표 형식 즉, `float`의 값 형식을 갖는 연관된 질감과 동일한 차원의 `short_vector`입니다.|  
|`gather_return_type`|수집 작업에 사용된 반환 형식입니다. 즉, 샘플링된 4가지 텍셀 값에서 수집된 4개의 동종 색상 구성 요소를 보유하는 4차원 `short_vector`입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[texture\_view::texture\_view 생성자](../Topic/texture_view::texture_view%20Constructor.md)|오버로드됨.  `texture_view` 인스턴스를 생성합니다.|  
|[texture\_view::~texture\_view 소멸자](../Topic/texture_view::~texture_view%20Destructor.md)|`texture_view` 인스턴스를 제거합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[texture\_view::gather\_alpha 메서드](../Topic/texture_view::gather_alpha%20Method.md)|오버로드됨.  지정된 샘플링 구성을 사용하여 지정된 좌표에 질감을 샘플링하고 4개의 샘플링된 텍셀의 알파\(w\) 구성 요소를 반환합니다.|  
|[texture\_view::gather\_blue 메서드](../Topic/texture_view::gather_blue%20Method.md)|오버로드됨.  지정된 샘플링 구성을 사용하여 지정된 좌표에 질감을 샘플링하고 4개의 샘플링된 텍셀의 파란색\(z\) 구성 요소를 반환합니다.|  
|[texture\_view::gather\_green 메서드](../Topic/texture_view::gather_green%20Method.md)|오버로드됨.  지정된 샘플링 구성을 사용하여 지정된 좌표에 질감을 샘플링하고 4개의 샘플링된 텍셀의 녹색\(y\) 구성 요소를 반환합니다.|  
|[texture\_view::gather\_red 메서드](../Topic/texture_view::gather_red%20Method.md)|오버로드됨.  지정된 샘플링 구성을 사용하여 지정된 좌표에 질감을 샘플링하고 4개의 샘플링된 텍셀의 빨간색\(x\) 구성 요소를 반환합니다.|  
|[texture\_view::get 메서드](../Topic/texture_view::get%20Method.md)|오버로드됨.  요소 값을 인덱스로 가져옵니다.|  
|[texture\_view::sample 메서드](../Topic/texture_view::sample%20Method.md)|오버로드됨.  텍스처 세부 수준과 지정된 좌표에 지정된 샘플링 구성을 사용하여 샘플링합니다.|  
|[texture\_view::set 메서드](../Topic/texture_view::set%20Method.md)|인덱스로 요소의 값을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[texture\_view::operator\(\) 연산자](../Topic/texture_view::operator\(\)%20Operator.md)|오버로드됨.  요소 값을 인덱스로 가져옵니다.|  
|[texture\_view::operatorOperator](../Topic/texture_view::operatorOperator.md)|오버로드됨.  요소 값을 인덱스로 가져옵니다.|  
|[texture\_view::operator\= 연산자](../Topic/texture_view::operator=%20Operator.md)|오버로드됨.  할당 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[texture\_view::value\_type 데이터 멤버](../Topic/texture_view::value_type%20Data%20Member.md)|`texture_view`의 요소에 대한 값 형식입니다.|  
  
## 상속 계층  
 `_Texture_base`  
  
 `texture_view`  
  
## 요구 사항  
 **헤더:** amp\_graphics.h  
  
 **네임스페이스:** concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)