---
title: "Deferrableeventargs:: Getdeferral 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a49fba82867650a80f45de3c6301405f96b5c47
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="deferrableeventargsgetdeferral-method"></a>DeferrableEventArgs::GetDeferral 메서드
에 대 한 참조는 [Deferral](http://go.microsoft.com/fwlink/p/?linkid=526520) 지연된 된 이벤트를 나타내는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `result`  
 참조 하는 포인터는 [Deferral](http://go.microsoft.com/fwlink/p/?linkid=526520) 호출이 완료 되 면 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 코드 예제를 참조 하십시오. [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)