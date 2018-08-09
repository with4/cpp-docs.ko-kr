---
title: 'Weakref:: Asiid 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e5ff6510463a6fed06534236612feb460919e37
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643487"
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID 메서드
지정 된 `ComPtr` 포인터 매개 변수를 나타내는 지정 된 인터페이스 id입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *riid*  
 인터페이스 ID입니다.  
  
 *ptr*  
 이 작업이 완료 되 면 매개 변수를 나타내는 개체 *riid*합니다.  
  
## <a name="return-value"></a>반환 값  
  
-   이 작업이 성공 하면 s_ok이 고 이유를 나타내는 HRESULT 그렇지 않으면 작업이 실패 하 고 *ptr* 로 설정 된 **nullptr**합니다.  
  
-   하지만 현재가이 작업이 성공 하면 S_OK **WeakRef** 개체는 이미 해제 되었습니다. 매개 변수 *ptr* 로 설정 된 **nullptr**합니다.  
  
-   하지만 현재가이 작업이 성공 하면 S_OK **WeakRef** 개체가 매개 변수에서 파생 되지 않습니다 *riid*합니다. 매개 변수 *ptr* 로 설정 된 **nullptr**합니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## <a name="remarks"></a>설명  
 오류가 발생 하는 경우에 내보내집니다 매개 변수 *riid* 에서 파생 되지 않은 `IInspectable`합니다. 이 오류는 반환 값을 대체합니다.  
  
 첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿(여기에 표시되지 않지만 헤더 파일에서 선언됨)은 [자동](../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.  
  
 Windows 10 SDK 부터는이 메서드는 설정 되지 합니다 **WeakRef** 인스턴스의 **nullptr** 약한 참조를 가져올 수 없는 경우는 피할 수는 를확인하는오류검사코드**WeakRef** 에 대 한 **nullptr**합니다. 대신 확인 합니다 *ptr* 에 대 한 **nullptr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)