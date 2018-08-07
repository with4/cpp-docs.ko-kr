---
title: DeferrableEventArgs 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 72f5ee2beca3a3985258b12cea9091665eb74cfa
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571264"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs 클래스
지연에 대한 이벤트 인수 형식에 사용되는 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
```  
  
#### <a name="parameters"></a>매개 변수  
 *TEventArgsInterface*  
 지연된 이벤트에 대한 인수를 선언하는 인터페이스 형식입니다.  
  
 *TEventArgsClass*  
 구현 하는 클래스 *TEventArgsInterface*합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[DeferrableEventArgs::GetDeferral 메서드](../windows/deferrableeventargs-getdeferral-method.md)|에 대 한 참조를 가져옵니다 합니다 [지연](http://go.microsoft.com/fwlink/p/?linkid=526520) 지연된 된 이벤트를 나타내는 개체입니다.|  
|[DeferrableEventArgs::InvokeAllFinished 메서드](../windows/deferrableeventargs-invokeallfinished-method.md)|지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스의 인스턴스는 지연된 이벤트에 대한 이벤트 처리기에 전달됩니다. 템플릿 매개 변수는 특정 형식의 지연된 이벤트에 대한 이벤트 인수 세부 정보를 정의하는 인터페이스 및 해당 인터페이스를 구현하는 클래스를 나타냅니다.  
  
 클래스는 지연된 이벤트에 대한 이벤트 처리기에 첫 번째 인수로 표시됩니다. 호출할 수 있습니다 합니다 [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) 메서드를 합니다 [지연](http://go.microsoft.com/fwlink/p/?linkid=526520) 지연 된 이벤트에 대 한 모든 정보를 가져올 수 있는 개체입니다. 이벤트 처리를 완료한 후 Deferral 개체에 대해 Complete를 호출해야 합니다. 호출 해야 [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) 끝에 이벤트 처리기 메서드를 확인 하는 모든 지연 된 이벤트의 완료가 제대로 전달 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)