---
title: "HandleT 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs: C++
helpviewer_keywords: HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ff7261735149abb8db607c5fc0cd4aa837fdfd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handlet-class"></a>HandleT 클래스
개체에 대한 핸들을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `HandleTraits`  
 인스턴스는 [HandleTraits](../windows/handletraits-structure.md) 핸들의 일반적인 특성을 정의 하는 구조체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Traits`|`HandleTraits`의 동의어입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::HandleT 생성자](../windows/handlet-handlet-constructor.md)|HandleT 클래스의 새 인스턴스를 초기화합니다.|  
|[HandleT::~HandleT 소멸자](../windows/handlet-tilde-handlet-destructor.md)|HandleT 클래스의 인스턴스 초기화를 취소 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::Attach 메서드](../windows/handlet-attach-method.md)|현재 HandleT 개체가 지정된 된 핸들에 연결합니다.|  
|[HandleT::Close 메서드](../windows/handlet-close-method.md)|현재 HandleT 개체를 닫습니다.|  
|[HandleT::Detach 메서드](../windows/handlet-detach-method.md)|현재 HandleT 개체에서 기본 핸들을 분리합니다.|  
|[HandleT::Get 메서드](../windows/handlet-get-method.md)|기본 핸들의 값을 가져옵니다.|  
|[HandleT::IsValid 메서드](../windows/handlet-isvalid-method.md)|현재 HandleT 개체가 핸들을 나타내는지 여부를 나타냅니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::InternalClose 메서드](../windows/handlet-internalclose-method.md)|현재 HandleT 개체를 닫습니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::operator= 연산자](../windows/handlet-operator-assign-operator.md)|현재 HandleT 개체를 지정된 된 HandleT 개체의 값을 이동합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[HandleT::handle_ Data 멤버](../windows/handlet-handle-data-member.md)|HandleT 개체가 핸들을 포함 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HandleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)