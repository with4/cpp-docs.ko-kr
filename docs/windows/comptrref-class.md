---
title: ComPtrRef 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c45aa289b4b41ddfaf141dcaf790734284af7c8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643552"
---
# <a name="comptrref-class"></a>ComPtrRef 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 A [ComPtr\<T >](../windows/comptr-class.md) 형식 또는 형식에서 파생 하 여이 나타내는 인터페이스 뿐만 아니라는 `ComPtr`합니다.  
  
## <a name="remarks"></a>설명  
 형식의 개체에 대 한 참조를 나타내는 `ComPtr<T>`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef 생성자](../windows/comptrref-comptrref-constructor.md)|새 인스턴스를 초기화 합니다 **ComPtrRef** 지정 된 포인터를 클래스 **ComPtrRef** 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf 메서드](../windows/comptrref-getaddressof-method.md)|현재이 나타내는 인터페이스에 대 한 포인터의 주소를 검색 **ComPtrRef** 개체입니다.|  
|[ComPtrRef::ReleaseAndGetAddressOf 메서드](../windows/comptrref-releaseandgetaddressof-method.md)|현재 삭제 **ComPtrRef** 개체 및 포인터-에-a-포인터를 반환에서 나타내는 인터페이스를 **ComPtrRef** 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType** 연산자](../windows/comptrref-operator-interfacetype-star-star-operator.md)|현재 삭제 **ComPtrRef** 개체 및 포인터-에-a-포인터를 반환에서 나타내는 인터페이스를 **ComPtrRef** 개체입니다.|  
|[ComPtrRef::operator T* 연산자](../windows/comptrref-operator-t-star-operator.md)|값을 반환 합니다 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 현재 ComPtrRef 개체의 데이터 멤버입니다.|  
|[ComPtrRef::operator void** 연산자](../windows/comptrref-operator-void-star-star-operator.md)|현재 삭제 **ComPtrRef** 개체에서 나타내는 인터페이스에 대 한 포인터 캐스팅, 합니다 **ComPtrRef** 개체에 대 한 포인터--포인터-을 변수로 **void**, 차례로 캐스트 포인터를 반환합니다.|  
|[ComPtrRef::operator* 연산자](../windows/comptrref-operator-star-operator.md)|현재이 나타내는 인터페이스에 포인터를 검색 **ComPtrRef** 개체입니다.|  
|[ComPtrRef::operator== 연산자](../windows/comptrref-operator-equality-operator.md)|나타냅니다 두 **ComPtrRef** 개체는 동일 합니다.|  
|[ComPtrRef::operator!= 연산자](../windows/comptrref-operator-inequality-operator.md)|나타냅니다 두 **ComPtrRef** 개체가 같지 않습니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)