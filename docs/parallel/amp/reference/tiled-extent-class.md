---
title: "tiled_extent 클래스 | Microsoft Docs"
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
  - "amp/Concurrency::tiled_extent"
dev_langs: 
  - "C++"
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# tiled_extent 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`tiled_extent` 개체는 확장 공간을 1, 2 또는 3차원 타일로 세분하는 1~3차원 중 하나의 `extent` 개체입니다.  
  
## 구문  
  
```  
template <  
   int _Dim0,  
   int _Dim1,  
   int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
  
template <  
   int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
```  
  
#### 매개 변수  
 `_Dim0`  
 최대 유효 치수의 길이입니다.  
  
 `_Dim1`  
 두 번째 중요한 크기의 길이입니다.  
  
 `_Dim2`  
 최소 유효 치수의 길이입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[tiled\_extent::tiled\_extent 생성자](../Topic/tiled_extent::tiled_extent%20Constructor.md)|`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[tiled\_extent::get\_tile\_extent 메서드](../Topic/tiled_extent::get_tile_extent%20Method.md)|`tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1` 및 `_Dim2`의 값을 캡처하는 `extent` 개체를 반환합니다.|  
|[tiled\_extent::pad 메서드](../Topic/tiled_extent::pad%20Method.md)|타일 크기에 따라 균등하게 나눌 수 있도록 높게 조정된 범위의 새 `tiled_extent` 개체를 반환합니다.|  
|[tiled\_extent::truncate 메서드](../Topic/tiled_extent::truncate%20Method.md)|타일 크기에 따라 균등하게 나눌 수 있도록 낮게 조정된 범위의 새 `tiled_extent` 개체를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[tiled\_extent::operator\= 연산자](../Topic/tiled_extent::operator=%20Operator.md)|지정된 `tiled_index` 개체의 내용을 여기로 복사합니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[tiled\_extent::tile\_dim0 상수](../Topic/tiled_extent::tile_dim0%20Constant.md)|최대 유효 치수의 길이를 저장합니다.|  
|[tiled\_extent::tile\_dim1 상수](../Topic/tiled_extent::tile_dim1%20Constant.md)|다음 최대 유효 치수의 길이를 저장합니다.|  
|[tiled\_extent::tile\_dim2 상수](../Topic/tiled_extent::tile_dim2%20Constant.md)|최소 유효 치수의 길이를 저장합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[tiled\_extent::tile\_extent 데이터 멤버](../Topic/tiled_extent::tile_extent%20Data%20Member.md)|`tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1` 및 `_Dim2`의 값을 캡처하는 `extent` 개체를 가져옵니다.|  
  
## 상속 계층  
 `extent`  
  
 `tiled_extent`  
  
## 요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)