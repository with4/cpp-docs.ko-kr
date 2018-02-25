---
title: "short_vector 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- short_vector
- AMP_SHORT_VECTORS/short_vector
- AMP_SHORT_VECTORS/Concurrency::graphics::short_vector::short_vector Constructor
dev_langs:
- C++
ms.assetid: e4f50b8f-1150-437d-b58c-79c5fb883708
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d71ef4577845319bf66ef51e92afae7907526008
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="shortvector-structure"></a>short_vector 구조체
short_vector는 일반적으로 짧은 벡터 프로그래밍에 유용한 메타프로그래밍 정의를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `_Scalar_type`  
 `_Size`  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`type`||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[short_vector:: short_vector 생성자](#ctor)||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `short_vector`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_short_vectors.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="ctor">short_vector:: short_vector 생성자</a>  
  
```  
short_vector();
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
