---
title: "동시성 네임 스페이스 상수의 (AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: 852408f309c00aa284ce710a3612d0654ed7b768
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-constants-amp"></a>동시성 네임 스페이스 상수의 (AMP)
|||  
|-|-|  
|[HLSL_MAX_NUM_BUFFERS 상수](#hlsl_max_num_buffers)|[MODULENAME_MAX_LENGTH 상수](#modulename_max_length)|  
  
##  <a name="a-namehlslmaxnumbuffersa--hlslmaxnumbuffers-constant"></a><a name="hlsl_max_num_buffers"></a>HLSL_MAX_NUM_BUFFERS 상수  
 DirectX에 의해 허용 되는 버퍼의 최대 수입니다.  
  
```  
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;  
```  
  
##  <a name="a-namemodulenamemaxlengtha--modulenamemaxlength-constant"></a><a name="modulename_max_length"></a>MODULENAME_MAX_LENGTH 상수  
 모듈 이름의 최대 길이 저장합니다. 이 값은 컴파일러와 런타임에서 동일해야 합니다.  
  
```  
static const UINT MODULENAME_MAX_LENGTH = 1024;  
```  
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

