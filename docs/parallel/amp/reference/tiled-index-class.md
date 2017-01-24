---
title: "tiled_index 클래스 | Microsoft Docs"
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
  - "amp/Concurrency::tiled_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tiled_index 클래스"
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: 19
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# tiled_index 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

[tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md)개체의 인덱스를 제공합니다.  이 클래스에는 로컬 타일 원본 및 전역 원본과 관련된 요소에 액세스하기 위한 속성이 있습니다.  바둑판식 공간에 대한 자세한 내용은 [타일 사용](../../../parallel/amp/using-tiles.md)을 참조하십시오.  
  
## 구문  
  
```  
template <  
   int _Dim0,  
   int _Dim1 = 0,  
   int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
  
template <  
   int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
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
|[tiled\_index::tiled\_index 생성자](../Topic/tiled_index::tiled_index%20Constructor.md)|`tile_index` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[tiled\_index::get\_tile\_extent 메서드](../Topic/tiled_index::get_tile_extent%20Method.md)|[tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) 템플릿 인수 `_Dim0`, `_Dim1` 및 `_Dim2`의 값을 가진 [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) 개체를 반환합니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[tiled\_index::barrier 상수](../Topic/tiled_index::barrier%20Constant.md)|스레드의 현재 타일에 장애물을 나타내는 [tile\_barrier](../../../parallel/amp/reference/tile-barrier-class.md) 개체를 저장합니다.|  
|||  
|[tiled\_index::global 상수](../Topic/tiled_index::global%20Constant.md)|[그리드](http://msdn.microsoft.com/ko-kr/f7d1b6a6-586c-4345-b09a-bfc26c492cb0) 개체에서 전역 인덱스를 나타내는 차수 1, 2 또는 3의 [인덱스](../../../parallel/amp/reference/index-class.md) 개체를 저장합니다.|  
|[tiled\_index::local 상수](../Topic/tiled_index::local%20Constant.md)|[tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md) 개체의 현재 타일의 상대 인덱스를 나타내는 차수 1, 2 또는 3의 `index` 개체를 저장합니다.|  
|[tiled\_index::rank 상수](../Topic/tiled_index::rank%20Constant.md)|[바둑판식 인덱스](../../../parallel/amp/reference/tiled-index-class.md) 개체의 순위를 저장합니다.|  
|[tiled\_index::tile 상수](../Topic/tiled_index::tile%20Constant.md)|`tiled_extent` 개체의 현재 타일의 좌표를 나타내는 차수 1, 2 또는 3의 `index` 개체를 저장합니다.|  
|[tiled\_index::tile\_dim0 상수](../Topic/tiled_index::tile_dim0%20Constant.md)|최대 유효 치수의 길이를 저장합니다.|  
|[tiled\_index::tile\_dim1 상수](../Topic/tiled_index::tile_dim1%20Constant.md)|다음 최대 유효 치수의 길이를 저장합니다.|  
|[tiled\_index::tile\_dim2 상수](../Topic/tiled_index::tile_dim2%20Constant.md)|최소 유효 치수의 길이를 저장합니다.|  
|[tiled\_index::tile\_origin 상수](../Topic/tiled_index::tile_origin%20Constant.md)|`tiled_extent` 개체의 현재 타일의 원점의 전역 좌표를 나타내는 차수 1, 2 또는 3의 `index` 개체를 저장합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[tiled\_index::tile\_extent 데이터 멤버](../Topic/tiled_index::tile_extent%20Data%20Member.md)|[tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) 템플릿 인수 [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) 템플릿 인수 `_Dim0`, `_Dim1` 및 `_Dim2`의 값을 가진 [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) 개체를 가져옵니다.|  
  
## 상속 계층  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## 요구 사항  
 **헤더:** amp.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)