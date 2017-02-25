---
title: "sampler 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# sampler 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

샘플러 클래스는 텍스처 샘플링에 사용되는 샘플링 구성 정보를 집계합니다.  
  
## 구문  
  
```  
class sampler;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[sampler::sampler 생성자](../Topic/sampler::sampler%20Constructor.md)|오버로드됨.  샘플러 인스턴스를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[sampler::get\_address\_mode 메서드](../Topic/sampler::get_address_mode%20Method.md)|샘플러 개체와 연관된 `address_mode`를 반환합니다.|  
|[sampler::get\_border\_color 메서드](../Topic/sampler::get_border_color%20Method.md)|샘플러 개체와 연관된 테두리 색을 반환합니다.|  
|[sampler::get\_filter\_mode 메서드](../Topic/sampler::get_filter_mode%20Method.md)|샘플러 개체와 연관된 `filter_mode`를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[sampler::operator\= 연산자](../Topic/sampler::operator=%20Operator.md)|오버로드됨.  할당 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[sampler::address\_mode 데이터 멤버](../Topic/sampler::address_mode%20Data%20Member.md)|주소 모드의 `sampler` 개체를 가져옵니다.|  
|[sampler::border\_color 데이터 멤버](../Topic/sampler::border_color%20Data%20Member.md)|`sampler` 개체의 테두리 색을 가져옵니다.|  
|[sampler::filter\_mode 데이터 멤버](../Topic/sampler::filter_mode%20Data%20Member.md)|필터 모드의 `sampler` 개체를 가져옵니다.|  
  
## 상속 계층  
 `sampler`  
  
## 요구 사항  
 **헤더:** amp\_graphics.h  
  
 **네임스페이스:** concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)