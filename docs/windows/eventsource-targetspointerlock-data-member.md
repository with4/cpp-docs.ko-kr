---
title: "Eventsource:: Targetspointerlock_ 데이터 멤버 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::targetsPointerLock_
dev_langs: C++
helpviewer_keywords: targetsPointerLock_ data member
ms.assetid: 8f08409f-5262-4be7-9cf1-2ed15f19684a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bd86ab088f23241b27e958749e54ee3ae2841a5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="eventsourcetargetspointerlock-data-member"></a>EventSource::targetsPointerLock_ 데이터 멤버
이 EventSource의 이벤트 처리기를 추가, 삭제 또는 호출하는 동안에도 내부 데이터 멤버에 대한 액세스를 동기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Wrappers::SRWLock targetsPointerLock_;  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [EventSource 클래스](../windows/eventsource-class.md)