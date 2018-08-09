---
title: 'Eventsource:: Getsize 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::GetSize
dev_langs:
- C++
helpviewer_keywords:
- GetSize method
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49497c8b33641521a66c3e84dc2dae3dbd993699
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645050"
---
# <a name="eventsourcegetsize-method"></a>EventSource::GetSize 메서드
현재 연결 된 이벤트 처리기의 수를 검색 **EventSource** 개체  
  
## <a name="syntax"></a>구문  
  
```cpp  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>반환 값  
 이벤트 처리기의 수가 [targets_](../windows/eventsource-targets-data-member.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [EventSource 클래스](../windows/eventsource-class.md)