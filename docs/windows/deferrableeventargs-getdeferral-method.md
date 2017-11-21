---
title: "Deferrableeventargs:: Getdeferral 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d43aa6d82f44965e8defda2af3e6455e86cba38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="deferrableeventargsgetdeferral-method"></a>DeferrableEventArgs::GetDeferral 메서드
에 대 한 참조는 [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) 지연된 된 이벤트를 나타내는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `result`  
 참조 하는 포인터는 [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) 호출이 완료 되 면 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 코드 예제를 참조 하십시오. [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)