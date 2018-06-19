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
ms.openlocfilehash: 75b9a07fd88caa9db7f2f145069b0d8857b79fe9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859692"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus 메서드
현재 비동기 작업의 상태를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `status`  
 이 작업의 현재 상태를 저장 하는 위치입니다.  
  
## <a name="remarks"></a>설명  
 이 작업은 스레드로부터 안전 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)   
 [AsyncStatusInternal 열거형](../windows/asyncstatusinternal-enumeration.md)