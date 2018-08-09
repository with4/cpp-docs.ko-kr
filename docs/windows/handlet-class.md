---
title: HandleT 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a34b66a6e2c901ddbfb3005a0bdb8fd686317af0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641507"
---
# <a name="handlet-class"></a>HandleT 클래스
개체에 대한 핸들을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
### <a name="parameters"></a>매개 변수  
 *HandleTraits*  
 인스턴스를 [HandleTraits](../windows/handletraits-structure.md) 핸들의 공통 된 특징을 정의 하는 구조입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Traits`|`HandleTraits`의 동의어입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::HandleT 생성자](../windows/handlet-handlet-constructor.md)|새 인스턴스를 초기화 합니다 **HandleT** 클래스입니다.|  
|[HandleT::~HandleT 소멸자](../windows/handlet-tilde-handlet-destructor.md)|인스턴스를 초기화 해제 합니다 **HandleT** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::Attach 메서드](../windows/handlet-attach-method.md)|현재 지정된 된 핸들과 연결 **HandleT** 개체입니다.|  
|[HandleT::Close 메서드](../windows/handlet-close-method.md)|현재 닫습니다 **HandleT** 개체입니다.|  
|[HandleT::Detach 메서드](../windows/handlet-detach-method.md)|현재 연결을 끊습니다 **HandleT** 해당 기본 핸들에서 개체입니다.|  
|[HandleT::Get 메서드](../windows/handlet-get-method.md)|기본 핸들의 값을 가져옵니다.|  
|[HandleT::IsValid 메서드](../windows/handlet-isvalid-method.md)|나타냅니다 여부 현재 **HandleT** 개체 핸들을 나타냅니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::InternalClose 메서드](../windows/handlet-internalclose-method.md)|현재 닫습니다 **HandleT** 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HandleT::operator= 연산자](../windows/handlet-operator-assign-operator.md)|지정 된 값을 이동 **HandleT** 개체를 현재 **HandleT** 개체입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[HandleT::handle_ Data 멤버](../windows/handlet-handle-data-member.md)|핸들을 나타내는 포함 된 **HandleT** 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HandleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)