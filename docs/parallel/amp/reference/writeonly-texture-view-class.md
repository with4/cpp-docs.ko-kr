---
title: "writeonly_texture_view 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::writeonly_texture_view"
dev_langs: 
  - "C++"
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# writeonly_texture_view 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

텍스쳐 쓰기 전용 액세스를 제공합니다.  
  
## 구문  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class writeonly_texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class writeonly_texture_view<_Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
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
|`scalar_type`||  
|`value_type`|질감에 있는 요소의 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[writeonly\_texture\_view::writeonly\_texture\_view 생성자](../Topic/writeonly_texture_view::writeonly_texture_view%20Constructor.md)|[writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md) 클래스의 새 인스턴스를 초기화합니다.|  
|[writeonly\_texture\_view::~writeonly\_texture\_view 소멸자](../Topic/writeonly_texture_view::~writeonly_texture_view%20Destructor.md)|[writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md) 개체를 제거합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[writeonly\_texture\_view::set 메서드](../Topic/writeonly_texture_view::set%20Method.md)|지정된 인덱스에서 요소 값을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[writeonly\_texture\_view::operator\= 연산자](../Topic/writeonly_texture_view::operator=%20Operator.md)|지정된 [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md) 개체를 여기로 복사합니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[writeonly\_texture\_view::rank 상수](../Topic/writeonly_texture_view::rank%20Constant.md)|[writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md) 개체의 차수를 가져옵니다.|  
  
## 상속 계층  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## 요구 사항  
 **헤더:** amp\_graphics.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)