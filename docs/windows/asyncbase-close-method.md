---
title: 'Asyncbase:: Close 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ce391e95aa9e08ae7d99e3cbdf064721ce21dbe
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643539"
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close 메서드
비동기 작업을 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>반환 값  
 작업이 이미 닫히거나 경우 s_ok이 고, 닫혀 않으면 그렇지 않으면 E_ILLEGAL_STATE_CHANGE 합니다.  
  
## <a name="remarks"></a>설명  
 **Close ()** 의 기본 구현 이며 `IAsyncInfo::Close`, 없습니다 실제 작업을 수행 합니다. 비동기 작업을 실제로 닫으려면 재정의 `OnClose()` 순수 가상 메서드가 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)