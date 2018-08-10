---
title: 'Weakref:: As 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7dd0dca806c1568d88c20eec6a7ac63e5fb242fb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020358"
---
# <a name="weakrefas-method"></a>WeakRef::As 메서드
지정 된 `ComPtr` 포인터 매개 변수를 지정된 된 인터페이스를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *U*  
 인터페이스 ID입니다.  
  
 *ptr*  
 이 작업이 완료 되 면 매개 변수를 나타내는 개체 *U*합니다.  
  
## <a name="return-value"></a>반환 값  
  
-   이 작업이 성공 하면 s_ok이 고 이유를 나타내는 HRESULT 그렇지 않으면 작업이 실패 하 고 *ptr* 로 설정 된 **nullptr**합니다.  
  
-   하지만 현재가이 작업이 성공 하면 S_OK **WeakRef** 개체는 이미 해제 되었습니다. 매개 변수 *ptr* 로 설정 된 **nullptr**합니다.  
  
-   하지만 현재가이 작업이 성공 하면 S_OK **WeakRef** 개체가 매개 변수에서 파생 되지 않습니다 *U*합니다. 매개 변수 *ptr* 로 설정 된 **nullptr**합니다.  
  
## <a name="remarks"></a>설명  
 오류가 발생 하는 경우에 내보내집니다 매개 변수 *U* 됩니다 `IWeakReference`에서 파생 되지 않은 또는 `IInspectable`합니다.  
  
 첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.  
  
 Windows 10 SDK 부터는이 메서드는 설정 되지 합니다 **WeakRef** 인스턴스의 **nullptr** 약한 참조를 가져올 수 없는 경우는 피할 수에 대해 WeakRef를 검사 하는 오류 검사 코드 **nullptr**합니다. 대신 확인 합니다 *ptr* 에 대 한 **nullptr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)