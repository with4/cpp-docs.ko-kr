---
title: "short_vector 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::short_vector"
dev_langs: 
  - "C++"
ms.assetid: e4f50b8f-1150-437d-b58c-79c5fb883708
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# short_vector 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

short\_vector는 일반적으로 짧은 벡처 프로그래밍에 유용한 메타프로그래밍 정의를 제공합니다.  
  
## 구문  
  
```  
template<  
   typename _Scalar_type,  
   int _Size  
>  
struct short_vector;  
template<>  
struct short_vector<unsigned int, 1>;  
template<>  
struct short_vector<unsigned int, 2>;  
template<>  
struct short_vector<unsigned int, 3>;  
template<>  
struct short_vector<unsigned int, 4>;  
template<>  
struct short_vector<int, 1>;  
template<>  
struct short_vector<int, 2>;  
template<>  
struct short_vector<int, 3>;  
template<>  
struct short_vector<int, 4>;  
template<>  
struct short_vector<float, 1>;  
template<>  
struct short_vector<float, 2>;  
template<>  
struct short_vector<float, 3>;  
template<>  
struct short_vector<float, 4>;  
template<>  
struct short_vector<unorm, 1>;  
template<>  
struct short_vector<unorm, 2>;  
template<>  
struct short_vector<unorm, 3>;  
template<>  
struct short_vector<unorm, 4>;  
template<>  
struct short_vector<norm, 1>;  
template<>  
struct short_vector<norm, 2>;  
template<>  
struct short_vector<norm, 3>;  
template<>  
struct short_vector<norm, 4>;  
template<>  
struct short_vector<double, 1>;  
template<>  
struct short_vector<double, 2>;  
template<>  
struct short_vector<double, 3>;  
template<>  
struct short_vector<double, 4>;  
```  
  
#### 매개 변수  
 `_Scalar_type`  
 `_Size`  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`type`||  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[short\_vector::short\_vector 생성자](../Topic/short_vector::short_vector%20Constructor.md)||  
  
## 상속 계층  
 `short_vector`  
  
## 요구 사항  
 **헤더:** amp\_short\_vectors.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)