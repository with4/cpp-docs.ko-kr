---
title: "RoInitializeWrapper 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f6330c78a6bbac5f14e94c253f05515e3d29575
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper 클래스
Windows 런타임을 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>설명  
 RoInitializeWrapper는 하는 Windows 런타임에서 초기화 작업이 성공 했는지 여부를 나타내는 HRESULT를 반환 합니다.  
  
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