---
title: "ComPtrRefBase 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 071598c83086afe12e1d19ef541dbfb3d0dbc55a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 A [ComPtr\<T >](../windows/comptr-class.md) 형식 또는 형식에서 파생 된 ComPtr이 나타내는 인터페이스 뿐만 아니라 합니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 기본 클래스를 나타냅니다는 [ComPtrRef](../windows/comptrref-class.md) 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`InterfaceType`|템플릿 매개 변수 형식에 대 한 동의어 `T`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable** 연산자](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버를 한 포인터-에-a-포인터-IInspectable 인터페이스입니다.|  
|[ComPtrRefBase::operator IUnknown** 연산자](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 는 포인터를-a-포인터-대상에 데이터 멤버는 IUnknown 인터페이스입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_ 데이터 멤버](../windows/comptrrefbase-ptr-data-member.md)|현재 템플릿 매개 변수에 의해 지정 된 형식에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)