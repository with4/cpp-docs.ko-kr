---
title: "ComPtrRef 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b1bbe134f15fdba6863f1725cbcc7effcb6d94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrref-class"></a>ComPtrRef 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 A [ComPtr\<T >](../windows/comptr-class.md) 형식 또는 형식에서 파생 된 ComPtr이 나타내는 인터페이스 뿐만 아니라 합니다.  
  
## <a name="remarks"></a>설명  
 ComPtr 형식의 개체에 대 한 참조를 나타냅니다.\<T >.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef 생성자](../windows/comptrref-comptrref-constructor.md)|다른 ComPtrRef 개체를 지정된 된 포인터를 ComPtrRef 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf 메서드](../windows/comptrref-getaddressof-method.md)|현재 ComPtrRef 개체에서이 나타내는 인터페이스에 대 한 포인터의 주소를 검색 합니다.|  
|[ComPtrRef::ReleaseAndGetAddressOf 메서드](../windows/comptrref-releaseandgetaddressof-method.md)|현재 ComPtrRef 개체를 삭제하고 포인터를 가리키는 포인터를 ComPtrRef 개체에서 나타낸 인터페이스로 반환합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType** 연산자](../windows/comptrref-operator-interfacetype-star-star-operator.md)|현재 ComPtrRef 개체를 삭제하고 포인터를 가리키는 포인터를 ComPtrRef 개체에서 나타낸 인터페이스로 반환합니다.|  
|[ComPtrRef::operator T* 연산자](../windows/comptrref-operator-t-star-operator.md)|값을 반환 된 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 현재 ComPtrRef 개체의 데이터 멤버입니다.|  
|[ComPtrRef::operator void** 연산자](../windows/comptrref-operator-void-star-star-operator.md)|현재 ComPtrRef 개체를 삭제, 다른 이름으로 포인터-에-포인터-ComPtrRef 개체에서 나타낸 인터페이스로에 대 한 포인터 캐스팅 `void`, 캐스트 포인터를 반환 합니다.|  
|[ComPtrRef::operator* 연산자](../windows/comptrref-operator-star-operator.md)|현재 ComPtrRef 개체에서이 나타내는 인터페이스에 대 한 포인터를 검색 합니다.|  
|[ComPtrRef::operator== 연산자](../windows/comptrref-operator-equality-operator.md)|두 개의 ComPtrRef 개체가 같은지 여부를 나타냅니다.|  
|[ComPtrRef::operator!= 연산자](../windows/comptrref-operator-inequality-operator.md)|두 개의 ComPtrRef 개체가 같지 않은지 여부를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)