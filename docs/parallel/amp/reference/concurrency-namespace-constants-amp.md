---
title: "동시성 네임 스페이스 상수의 (AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
dev_langs:
- C++
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f6893de5506d452cf4a2a60cf7b07ed03dfab18
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-constants-amp"></a>동시성 네임 스페이스 상수의 (AMP)
|||  
|-|-|  
|[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)|[MODULENAME_MAX_LENGTH](#modulename_max_length)|  
  
##  <a name="hlsl_max_num_buffers"></a>  HLSL_MAX_NUM_BUFFERS Constant  
 DirectX에서 허용 하는 버퍼의 최대 수입니다.  
  
```  
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;  
```  
  
##  <a name="modulename_max_length"></a>  MODULENAME_MAX_LENGTH Constant  
 모듈 이름의 최대 길이 저장합니다. 이 값은 컴파일러와 런타임에서 동일해야 합니다.  
  
```  
static const UINT MODULENAME_MAX_LENGTH = 1024;  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
