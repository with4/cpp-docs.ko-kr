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
ms.openlocfilehash: 32f75c838ea178b1313ab0bf9f005ff2a4c5d75b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652564"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID 메서드
반환 된 **ComPtr** 지정 된 인터페이스 ID로 식별 된 인터페이스를 나타내는 개체  
  
## <a name="syntax"></a>구문  
  
```cpp  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *riid*  
 인터페이스 ID입니다.  
  
 *p*  
 개체에 있는 경우 해당 ID가 인터페이스 *riid*,으로 지정한 인터페이스에 대 한 이중 간접 포인터는 *riid* 매개 변수가 고, 그렇지 않으면에 대 한 포인터 `IUnknown`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)