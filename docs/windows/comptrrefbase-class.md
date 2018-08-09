---
title: ComPtrRefBase 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18f7f08362c14ab0d09019a5b9348750c96ddbd7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643412"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 A [ComPtr\<T >](../windows/comptr-class.md) 형식 또는 형식에서 파생 하 여이 나타내는 인터페이스 뿐만 아니라는 **ComPtr**합니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 기본 클래스를 나타냅니다 합니다 [ComPtrRef](../windows/comptrref-class.md) 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`InterfaceType`|템플릿 매개 변수의 형식에 대 한 동의어 *T*합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable** 연산자](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버는 포인터--a-포인터-을는 `IInspectable` 인터페이스입니다.|  
|[ComPtrRefBase::operator IUnknown** 연산자](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버는 포인터--a-포인터-을는 `IUnknown` 인터페이스입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_ 데이터 멤버](../windows/comptrrefbase-ptr-data-member.md)|현재 템플릿 매개 변수로 지정 된 형식에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)