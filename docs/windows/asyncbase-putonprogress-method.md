---
title: 'Asyncbase:: Putonprogress 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::PutOnProgress
dev_langs:
- C++
helpviewer_keywords:
- PutOnProgress method
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a99eee63496632b8f0918ee888e6a824424b757d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649892"
---
# <a name="asyncbaseputonprogress-method"></a>AsyncBase::PutOnProgress 메서드
진행률 이벤트 처리기의 주소를 지정된 된 값으로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHOD(  
   PutOnProgress  
)(TProgress* progressHandler);  
```  
  
### <a name="parameters"></a>매개 변수  
 *progressHandler*  
 진행률 이벤트 처리기에 설정 된 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 E_ILLEGAL_METHOD_CALL 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)