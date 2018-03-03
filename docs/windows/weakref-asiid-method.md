---
title: "Weakref:: Asiid 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fdefa73ac14e807c5e4100fd81e1d931f4bf6e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID 메서드
지정된 인터페이스 ID를 나타내도록 지정된 ComPtr 포인터 매개 변수를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 인터페이스 ID입니다.  
  
 `ptr`  
 이 작업이 완료되었을 때 `riid`매개 변수를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
  
-   이 작업이 성공하면 S_OK이고, 실패하면 작업이 실패한 원인을 나타내는 HRESULT입니다. 그리고 `ptr` 이 `nullptr`로 설정됩니다.  
  
-   이 작업이 성공하면 S_OK이지만, 현재 WeakRef 개체는 이미 해제되었습니다. `ptr` 매개 변수가 `nullptr`로 설정됩니다.  
  
-   이 작업이 성공하면 S_OK이지만, 현재 WeakRef 개체가 `riid`매개 변수에서 파생되지 않습니다. `ptr` 매개 변수가 `nullptr`로 설정됩니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `riid` 매개 변수가 IInspectable에서 파생되지 않은 경우 오류가 발생합니다. 이 오류는 반환 값을 대체합니다.  
  
 첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿(여기에 표시되지 않지만 헤더 파일에서 선언됨)은 [자동](../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.  
  
 Windows 10 SDK부터는 약한 참조를 가져올 수 없는 경우 이 메서드에서 WeakRef 인스턴스를 `nullptr` 로 설정하지 않으므로 WeakRef에서 `nullptr`을 검사하는 오류 검사 코드를 사용하지 않아야 합니다. 대신, 확인 `ptr` 에 대 한 `nullptr`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)