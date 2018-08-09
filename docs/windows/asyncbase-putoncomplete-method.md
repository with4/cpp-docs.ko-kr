---
title: 'Asyncbase:: Putoncomplete 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::PutOnComplete
dev_langs:
- C++
helpviewer_keywords:
- PutOnComplete method
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e982e6f053b207b1d57ed5c0df483a9d9ab778eb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646974"
---
# <a name="asyncbaseputoncomplete-method"></a>AsyncBase::PutOnComplete 메서드
완료 이벤트 처리기의 주소를 지정된 된 값으로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHOD(  
   PutOnComplete  
)(TComplete* completeHandler);  
```  
  
### <a name="parameters"></a>매개 변수  
 *completeHandler*  
 완료 이벤트 처리기에 설정 된 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 E_ILLEGAL_METHOD_CALL 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)