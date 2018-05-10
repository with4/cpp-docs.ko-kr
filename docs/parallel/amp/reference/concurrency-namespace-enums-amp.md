---
title: 동시성 네임 스페이스 열거형 (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a67b5e77b8ab8c52e55dea96e64a3f16a4d70e39
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="concurrency-namespace-enums-amp"></a>동시성 네임 스페이스 열거형 (AMP)
|||  
|-|-|  
|[access_type 열거형](#access_type)|[queuing_mode 열거형](#queuing_mode)|  
  
##  <a name="access_type"></a>  access_type 열거형  
 열거형 형식을 사용 하는 다양 한 유형의 데이터에 대 한 액세스를 나타냅니다.  
  
```  
enum access_type;  
```  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`access_type_auto`|자동으로 가장 적합 한 선택 `access_type` 액셀러레이터 키에 대 한 합니다.|  
|`access_type_none`|전용입니다. 할당은 CPU 아니라 액셀러레이터 키에 액세스할 수만 있습니다.|  
|`access_type_read`|공유합니다. 할당은 액셀러레이터 키에 액세스할 수 및 CPU에서 읽을 수 있습니다.|  
|`access_type_read_write`|공유합니다. 할당은 액셀러레이터 키에 액세스할 수 및 CPU에 쓸 수 있습니다.|  
|`access_type_write`|공유합니다. 액셀러레이터 키에 액세스할 수을 읽을 수 있으며 쓰기 가능한 CPU에 할당 합니다.|  

  
##  <a name="queuing_mode"></a>  queuing_mode 열거형  
 액셀러레이터에서 지원 되는 큐 모드를 지정 합니다.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`queuing_mode_immediate`|예를 들어는 모든 지정 하는 큐 모드 명령을 [parallel_for_each 함수 (c + + AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), 호출자에 게 반환 되는 즉시 해당 가속기 장치에 전송 됩니다.|  
|`queuing_mode_automatic`|명령에 해당 하는 명령 큐에 지연 될 지를 지정 하는 큐 모드는 [accelerator_view](accelerator-view-class.md) 개체입니다. 명령은 장치에 전송 되어 때 [accelerator_view:: flush](accelerator-view-class.md#flush) 호출 됩니다.|   
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
