---
title: "Invokehelper:: Invoke 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
dev_langs:
- C++
helpviewer_keywords:
- Invoke method
ms.assetid: 98618815-c30e-4699-b3dd-203c91b1bf3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8707ac96c0417eddb015d7e802433bf071dda80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="invokehelperinvoke-method"></a>InvokeHelper::Invoke 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   Invoke  
)();  
STDMETHOD(  
   Invoke  
)(typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arg1`  
 인수 1입니다.  
  
 `arg2`  
 인수 2입니다.  
  
 `arg3`  
 인수 3입니다.  
  
 `arg4`  
 4 인수입니다.  
  
 `arg5`  
 인수 5입니다.  
  
 `arg6`  
 6 인수입니다.  
  
 `arg7`  
 7 인수입니다.  
  
 `arg8`  
 8 인수입니다.  
  
 `arg9`  
 9 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 지정 된 인수 개수가 포함 된 시그니처 이벤트 처리기를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InvokeHelper 구조체](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)