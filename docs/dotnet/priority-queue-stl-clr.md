---
title: priority_queue (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7d1459da07f7e392a2da1fbf5d6e9d72c8f4653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueue-stlclr"></a>priority_queue(STL/CLR)
이 템플릿 클래스는 다양 한 길이의 액세스가 제한 된 요소의 시퀀스를 정렬 된 제어 하는 개체를 설명 합니다. 컨테이너 어댑터를 사용 하 여 `priority_queue` 우선 순위 큐는 기본 컨테이너를 관리할 수 있습니다.  
  
 아래 설명에 `GValue` 동일 `Value` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Value^`합니다. 마찬가지로, `GContainer` 동일 `Container` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Container^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### <a name="parameters"></a>매개 변수  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
 컨테이너  
 기본 컨테이너의 형식입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[priority_queue::const_reference(STL/CLR)](../dotnet/priority-queue-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[priority_queue::container_type(STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)|기본 컨테이너의 형식입니다.|  
|[priority_queue::difference_type(STL/CLR)](../dotnet/priority-queue-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[priority_queue::generic_container(STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)|컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.|  
|[priority_queue::generic_value(STL/CLR)](../dotnet/priority-queue-generic-value-stl-clr.md)|컨테이너 어댑터에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[priority_queue::reference(STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[priority_queue::size_type(STL/CLR)](../dotnet/priority-queue-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[priority_queue::value_compare(STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)|두 요소에 대해 정렬 하는 대리자입니다.|  
|[priority_queue::value_type(STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[priority_queue::assign(STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)|모든 요소를 바꿉니다.|  
|[priority_queue::empty(STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[priority_queue::get_container(STL/CLR)](../dotnet/priority-queue-get-container-stl-clr.md)|기본 컨테이너에 액세스합니다.|  
|[priority_queue::pop(STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)|Hghest 우선 순위 요소를 제거합니다.|  
|[priority_queue::priority_queue(STL/CLR)](../dotnet/priority-queue-priority-queue-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[priority_queue::push(STL/CLR)](../dotnet/priority-queue-push-stl-clr.md)|새 요소를 추가 합니다.|  
|[priority_queue::size(STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)|요소 수를 계산합니다.|  
|[priority_queue::top(STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)|우선 순위가 가장 높은 요소에 액세스 합니다.|  
|[priority_queue::to_array(STL/CLR)](../dotnet/priority-queue-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
|[priority_queue::value_comp(STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)|두 요소에 대 한 순서 지정 대리자를 복사합니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[priority_queue::top_item(STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)|우선 순위가 가장 높은 요소에 액세스 합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[priority_queue::operator=(STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|IPriorityQueue\<값, 컨테이너 >|제네릭 컨테이너 어댑터를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 형식의 기본 컨테이너를 통해 제어 하는 시퀀스에 대 한 저장소를 해제 `Container`, 저장 하는 `Value` 요소 및 필요에 따라 증가 합니다. 우선 순위가 가장 높은 요소 (맨 위에 있는 요소) 쉽게 액세스할 수 있고 이동식와 힙 정렬 순서를 유지 합니다. 개체는 새 요소를 삽입 또는 방금 우선 순위가 가장 높은 요소를 구현 하는 우선 순위 큐를 제거할에 대 한 액세스를 제한 합니다.  
  
 형식의 개체를 저장된 하는 대리자를 호출 하 여 제어 하는 시퀀스를 정렬 하는 개체 [priority_queue:: value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)합니다. Priority_queue; 생성할 때 저장된 대리자 개체를 지정할 수 있습니다. 기본값은 비교 없는 대리자 개체를 지정 하면 `operator<(value_type, value_type)`합니다. 멤버 함수를 호출 하 여이 저장 된 개체를 액세스할 [priority_queue:: value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`합니다.  
  
 이러한 대리자 개체 형식의 값에 엄밀히 약한 정렬을 적용 해야 합니다 [priority_queue:: value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)합니다. 모든 두 개의 키 즉 `X` 및 `Y`:  
  
 `value_comp()(X, Y)`동일한 부울 결과를 반환 모든 호출 합니다.  
  
 경우 `value_comp()(X, Y)` 가 true 이면 `value_comp()(Y, X)` false 이어야 합니다.  
  
 경우 `value_comp()(X, Y)` 가 true 이면 `X` 앞에 정렬를 라고 `Y`합니다.  
  
 경우 `!value_comp()(X, Y) && !value_comp()(Y, X)` 가 true 이면 `X` 및 `Y` 순서 지정이 동일할에 있다고 합니다.  
  
 모든 요소에 대해 `X` 앞에 `Y` 제어 된 시퀀스의 `key_comp()(Y, X)` 은 false입니다. (기본 대리자 개체에 대 한 키는 결코 감소 값입니다.)  
  
 가장 높은 우선 순위 요소는 따라서 다른 요소 앞에 정렬 되지 않은 하는 요소 중 하나입니다.  
  
 기본 컨테이너 힙 정렬 하는 요소를 유지 되므로:  
  
 컨테이너는 임의 액세스 반복기를 지원 해야 합니다.  
  
 순서 지정이 동일할 요소는 푸시된 보다 다른 순서에 따라 팝 될 수 있습니다. (순서 안정적이 지 않은.)  
  
 따라서 기본 컨테이너 될 [deque (STL/CLR)](../dotnet/deque-stl-clr.md) 및 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)