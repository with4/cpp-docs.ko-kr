---
title: 'Weakref:: Copyto 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 817d984e995e7ac33ba80f978a282a8c0bac3e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo 메서드
사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `U`  
 IInspectable 인터페이스의 포인터입니다. `U` 가 IInspectable에서 파생되지 않으면 오류가 발생합니다.  
  
 `riid`  
 인터페이스 ID입니다. 오류가 발생 하는 경우 `riid` 에서 파생 되지 않은 **IWeakReference**합니다.  
  
 `ptr`  
 IInspectable 또는 IWeakReference의 이중 간접 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## <a name="remarks"></a>설명  
 반환 값 S_OK는 이 작업이 성공했음을 의미하지만 약한 참조가 강한 참조로 확인되었는지를 나타내지 않습니다. S_OK가 반환되면 `p` 매개 변수가 강한 참조인지 테스트합니다. 즉, `p` 매개 변수가 `nullptr`과 같지 않은지 테스트합니다.  
  
 Windows 10 SDK부터는 약한 참조를 가져올 수 없는 경우 이 메서드에서 WeakRef 인스턴스를 `nullptr` 로 설정하지 않으므로 `nullptr`에 대해 WeakRef를 검사하는 오류 검사 코드를 사용하지 않아야 합니다. 대신, 확인 `ptr` 에 대 한 `nullptr`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)