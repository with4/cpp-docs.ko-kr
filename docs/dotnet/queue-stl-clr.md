---
title: queue (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue
dev_langs:
- C++
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e65d5a364f5886df2bad976e3c34dc57266b70f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172746"
---
# <a name="queue-stlclr"></a>queue(STL/CLR)
이 템플릿 클래스는 다양 한 길이의 요소 시퀀스를 선입 선출 액세스 권한이 있는 제어 하는 개체를 설명 합니다. 컨테이너 어댑터를 사용 하 여 `queue` 큐로는 기본 컨테이너를 관리할 수 있습니다.  
  
 아래 설명에 `GValue` 동일 `Value` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Value^`합니다. 마찬가지로, `GContainer` 동일 `Container` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Container^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const_reference(STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[queue::container_type(STL/CLR)](../dotnet/queue-container-type-stl-clr.md)|기본 컨테이너의 형식입니다.|  
|[queue::difference_type(STL/CLR)](../dotnet/queue-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[queue::generic_container(STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)|컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.|  
|[queue::generic_value(STL/CLR)](../dotnet/queue-generic-value-stl-clr.md)|컨테이너 어댑터에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[queue::reference(STL/CLR)](../dotnet/queue-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[queue::size_type(STL/CLR)](../dotnet/queue-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[queue::value_type(STL/CLR)](../dotnet/queue-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[queue::assign(STL/CLR)](../dotnet/queue-assign-stl-clr.md)|모든 요소를 바꿉니다.|  
|[queue::back(STL/CLR)](../dotnet/queue-back-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[queue::empty(STL/CLR)](../dotnet/queue-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[queue::front(STL/CLR)](../dotnet/queue-front-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
|[queue::get_container(STL/CLR)](../dotnet/queue-get-container-stl-clr.md)|기본 컨테이너에 액세스합니다.|  
|[queue::pop(STL/CLR)](../dotnet/queue-pop-stl-clr.md)|첫 번째 요소를 제거합니다.|  
|[queue::push(STL/CLR)](../dotnet/queue-push-stl-clr.md)|새 마지막 요소를 추가 합니다.|  
|[queue::queue(STL/CLR)](../dotnet/queue-queue-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[queue::size(STL/CLR)](../dotnet/queue-size-stl-clr.md)|요소 수를 계산합니다.|  
|[queue::to_array(STL/CLR)](../dotnet/queue-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[queue::back_item(STL/CLR)](../dotnet/queue-back-item-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[queue::front_item(STL/CLR)](../dotnet/queue-front-item-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[queue::operator=(STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
|[operator!= (queue)(STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)|있는지 여부를 확인 한 `queue` 개체가 다른과 같지 않습니다. `queue` 개체입니다.|  
|[operator< (queue)(STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)|있는지 여부를 확인 한 `queue` 개체를 사용 하면 다른 노드보다 작은지 `queue` 개체입니다.|  
|[operator<= (queue)(STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|있는지 여부를 확인 한 `queue` 개체 보다 작거나 같으면 다른 `queue` 개체입니다.|  
|[operator== (queue)(STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)|있는지 여부를 확인 한 `queue` 개체는 다른 `queue` 개체입니다.|  
|[operator> (queue)(STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)|있는지 여부를 확인 한 `queue` 개체가 다른 노드보다 큰지 `queue` 개체입니다.|  
|[operator>= (queue)(STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|있는지 여부를 확인 한 `queue` 개체는 다른 보다 크거나 `queue` 개체입니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|IQueue\<값, 컨테이너 >|제네릭 컨테이너 어댑터를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 형식의 기본 컨테이너를 통해 제어 하는 시퀀스에 대 한 저장소를 해제 `Container`, 저장 하는 `Value` 요소 및 필요에 따라 증가 합니다. 첫 번째 요소를 하나만 개체 액세스를 제한 하 고 (FIFO 큐 또는 큐 단순히 라고도 함) 큐 선입 선출 구현 마지막 요소를 팝 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)