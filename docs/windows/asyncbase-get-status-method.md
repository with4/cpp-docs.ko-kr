---
title: "Asyncbase:: Get_status 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::get_Status
dev_langs: C++
helpviewer_keywords: get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f7ac7e7a42d0cde4507f812a270548acfb5a69e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasegetstatus-method"></a>AsyncBase::get_Status 메서드
비동기 작업의 상태를 나타내는 값을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   get_Status  
)(AsyncStatus *status) override;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `status`  
 상태가 저장할 수 있는 위치입니다. 자세한 내용은 Windows::Foundation::AsyncStatus 열거형을 참조 하십시오.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 E_ILLEGAL_METHOD_CALL 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 IAsyncInfo::get_Status를 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)