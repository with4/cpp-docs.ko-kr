---
title: "동시성 네임 스페이스 열거형 (AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9555023e01cb765ca943fcaaf785cdc2b4e2d0d
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums-amp"></a>동시성 네임 스페이스 열거형 (AMP)
|||  
|-|-|  
|[access_type 열거형](#access_type)|[queuing_mode 열거형](#queuing_mode)|  
  
##  <a name="a-nameaccesstypea--accesstype-enumeration"></a><a name="access_type"></a>access_type 열거형  
 다양 한 유형의 데이터에 대 한 액세스를 나타내는 데 사용 되는 열거형 형식입니다.  
  
```  
enum access_type;  
```  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`access_type_auto`|자동으로 최상의 선택 `access_type` 가속기 합니다.|  
|`access_type_none`|전용. 할당은 CPU 아닌 액셀러레이터 키에 액세스할 수만 있습니다.|  
|`access_type_read`|공유합니다. 할당 된 가속기에 액세스할 수 및 CPU에서 읽을 수 있습니다.|  
|`access_type_read_write`|공유합니다. 할당 된 가속기에 액세스할 수 및 CPU에 쓸 수 있습니다.|  
|`access_type_write`|공유합니다. 할당은 액셀러레이터 키에 액세스할 수 이며 모두 읽고 쓸 수 있는 CPU에 있습니다.|  

  
##  <a name="a-namequeuingmodea--queuingmode-enumeration"></a><a name="queuing_mode"></a>queuing_mode 열거형  
 액셀러레이터에서 지원 되는 큐 모드를 지정 합니다.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`queuing_mode_immediate`|예를 들어는 모든 지정 하는 큐 모드 명령 [parallel_for_each 함수 (c + + AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), 호출자에 게 반환 되는 즉시 해당 가속기 장치에 전송 됩니다.|  
|`queuing_mode_automatic`|명령에 해당 하는 명령 큐의 큐 수를 지정 하는 큐 모드는 [accelerator_view](accelerator-view-class.md) 개체입니다. 명령은 장치에 전송 되어 때 [accelerator_view:: flush](accelerator-view-class.md#flush) 호출 됩니다.|   
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

