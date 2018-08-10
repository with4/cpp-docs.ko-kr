---
title: 'Asyncbase:: Currentstatus 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36c3f76e3fc137458acddacd834563d845057a24
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646577"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus 메서드
현재 비동기 작업의 상태를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *status*  
 이 작업의 현재 상태를 저장 하는 위치를 위치입니다.  
  
## <a name="remarks"></a>설명  
 이 작업은 스레드로부터 안전 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)   
 [AsyncStatusInternal 열거형](../windows/asyncstatusinternal-enumeration.md)