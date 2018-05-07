---
title: stack (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack
dev_langs:
- C++
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 290857b51fea6726ec7e4a836d4afe1b33a8e615
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="stack-stlclr"></a>stack(STL/CLR)
이 템플릿 클래스는 다양 한 길이의 요소 시퀀스를 마지막 액세스할 수 있는 제어 하는 개체를 설명 합니다. 컨테이너 어댑터를 사용 하 여 `stack` 스택으로 푸시 다운 하는 기본 컨테이너를 관리할 수 있습니다.  
  
 아래 설명에 `GValue` 동일 `Value` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Value^`합니다. 마찬가지로, `GContainer` 동일 `Container` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Container^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
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
|[stack::const_reference(STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[stack::container_type(STL/CLR)](../dotnet/stack-container-type-stl-clr.md)|기본 컨테이너의 형식입니다.|  
|[stack::difference_type(STL/CLR)](../dotnet/stack-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[stack::generic_container(STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)|컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.|  
|[stack::generic_value(STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)|컨테이너 어댑터에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[stack::reference(STL/CLR)](../dotnet/stack-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[stack::size_type(STL/CLR)](../dotnet/stack-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[stack::value_type(STL/CLR)](../dotnet/stack-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[stack::assign(STL/CLR)](../dotnet/stack-assign-stl-clr.md)|모든 요소를 바꿉니다.|  
|[stack::empty(STL/CLR)](../dotnet/stack-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[stack::get_container(STL/CLR)](../dotnet/stack-get-container-stl-clr.md)|기본 컨테이너에 액세스합니다.|  
|[stack::pop(STL/CLR)](../dotnet/stack-pop-stl-clr.md)|마지막 요소를 제거 합니다.|  
|[stack::push(STL/CLR)](../dotnet/stack-push-stl-clr.md)|새 마지막 요소를 추가 합니다.|  
|[stack::size(STL/CLR)](../dotnet/stack-size-stl-clr.md)|요소 수를 계산합니다.|  
|[stack::stack(STL/CLR)](../dotnet/stack-stack-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[stack::top(STL/CLR)](../dotnet/stack-top-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[stack::to_array(STL/CLR)](../dotnet/stack-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[stack::top_item(STL/CLR)](../dotnet/stack-top-item-stl-clr.md)|마지막 요소에 액세스합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[stack::operator=(STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
|[operator!= (stack)(STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)|있는지 여부를 확인 한 `stack` 개체가 다른과 같지 않습니다. `stack` 개체입니다.|  
|[operator< (stack)(STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)|있는지 여부를 확인 한 `stack` 개체를 사용 하면 다른 노드보다 작은지 `stack` 개체입니다.|  
|[operator<= (stack)(STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|있는지 여부를 확인 한 `stack` 개체 보다 작거나 같으면 다른 `stack` 개체입니다.|  
|[operator== (stack)(STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)|있는지 여부를 확인 한 `stack` 개체는 다른 `stack` 개체입니다.|  
|[operator> (stack)(STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)|있는지 여부를 확인 한 `stack` 개체가 다른 노드보다 큰지 `stack` 개체입니다.|  
|[operator>= (stack)(STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|있는지 여부를 확인 한 `stack` 개체는 다른 보다 크거나 `stack` 개체입니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|IStack\<값, 컨테이너 >|제네릭 컨테이너 어댑터를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 형식의 기본 컨테이너를 통해 제어 하는 시퀀스에 대 한 저장소를 해제 `Container`, 저장 하는 `Value` 요소 및 필요에 따라 증가 합니다. 개체를 삽입 또는 제거할 방금 마지막 요소를 구현 (라고도 LIFO 큐 또는 스택) 마지막 큐 액세스를 제한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/스택 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)