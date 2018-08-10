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
ms.openlocfilehash: 88a092255655aaea0e06e8f69b520789f441d379
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016290"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo 메서드
사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
### <a name="parameters"></a>매개 변수  
 *U*  
 포인터는 `IInspectable` 인터페이스입니다. 오류가 발생 하는 경우에 내보내집니다 *U* 에서 파생 되지 않은 `IInspectable`합니다.  
  
 *riid*  
 인터페이스 ID입니다. 오류가 발생 하는 경우에 내보내집니다 *riid* 에서 파생 되지 않은 `IWeakReference`합니다.  
  
 *ptr*  
 에 대 한 이중 간접 포인터 `IInspectable` 또는 `IWeakReference`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. 자세한 내용은 **설명**을 참조하세요.  
  
## <a name="remarks"></a>설명  
 반환 값 S_OK는 이 작업이 성공했음을 의미하지만 약한 참조가 강한 참조로 확인되었는지를 나타내지 않습니다. S_OK가 반환 되 면 해당 매개 변수를 테스트 *p* 는 강력한 참조 매개 변수, 즉 *p* 같지 **nullptr**합니다.  
  
 Windows 10 SDK 부터는이 메서드는 설정 하지는 **WeakRef** 인스턴스의 **nullptr** 약한 참조를 가져올 수 없는 경우는 피할 수 오류 WeakRef를 검사 하는 코드를 검사 합니다. **nullptr**합니다. 대신 확인 합니다 *ptr* 에 대 한 **nullptr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)