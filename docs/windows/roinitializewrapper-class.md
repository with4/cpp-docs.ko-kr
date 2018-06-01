---
title: RoInitializeWrapper 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 05/20/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cac71857e6b472f11d1c9eaba48d181ea78fb456
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705594"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper 클래스
Windows 런타임을 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>설명  
 RoInitializeWrapper는 하는 Windows 런타임에서 초기화 작업이 성공 했는지 여부를 나타내는 HRESULT를 반환 합니다. 클래스 소멸자를 호출 하기 때문에 `::Windows::Foundation::Uninitialize`, 인스턴스의 `RoInitializeWrapper` 최상위 또는 전역 범위에서 선언 해야 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper 생성자](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|RoInitializeWrapper 클래스의 새 인스턴스를 초기화합니다.|  
|[RoInitializeWrapper::~RoInitializeWrapper 소멸자](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|RoInitializeWrapper 클래스의 현재 인스턴스를 제거합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT() 연산자](../windows/roinitializewrapper-hresult-parens-operator.md)|RoInitializeWrapper 생성자에서 만드는 HRESULT를 가져옵니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)