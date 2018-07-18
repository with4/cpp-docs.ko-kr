---
title: 'Comptr:: Asiid 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db5bc6b2547fb77dd887f96b6c33dee536e43f77
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025905"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID 메서드
지정된 인터페이스 ID로 식별된 인터페이스를 나타내는 ComPtr 개체를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 인터페이스 ID입니다.  
  
 `p`  
 개체에 있는 경우 해당 ID가 인터페이스 `riid`,으로 지정한 인터페이스에 대 한 이중 간접 포인터는 `riid` 매개 변수가 고, 그렇지 않으면 IUnknown에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)