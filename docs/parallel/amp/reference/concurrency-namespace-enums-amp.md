---
title: "동시성 네임 스페이스 열거형 (AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d17378a34698cc80d356983898e0023b76877140
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-enums-amp"></a>동시성 네임 스페이스 열거형 (AMP)
|||  
|-|-|  
|[access_type Enumeration](#access_type)|[queuing_mode 열거형](#queuing_mode)|  
  
##  <a name="access_type"></a>  access_type Enumeration  
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

  
##  <a name="queuing_mode"></a>  queuing_mode Enumeration  
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
