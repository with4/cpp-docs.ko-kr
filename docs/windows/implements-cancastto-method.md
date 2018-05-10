---
title: 'Implements:: cancastto 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4fd6e6736c74e1ce895031e17c1d5268eb4ce646
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo 메서드
지정된 된 인터페이스에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 인터페이스 ID에 대 한 참조  
  
 `ppv`  
 성공 하면 인터페이스에 대 한 포인터에 지정 된 `riid`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 E_NOINTERFACE 같은 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 이것이 QueryInterface 작업을 수행 하는 내부 도우미 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Implements 구조체](../windows/implements-structure.md)