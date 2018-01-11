---
title: deque (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque
dev_langs: C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9bd847b2641e6670a91d2edf1eb926aca423ad2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="deque-stlclr"></a>deque(STL/CLR)
템플릿 클래스는 임의 액세스를 가진 요소의 다양 한 길이의 시퀀스를 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 여 `deque` 인접 한 블록 저장소의 처럼 보입니다. 하지만 늘리거나 모든 나머지 요소를 복사할 필요 없이 양쪽 끝 줄일 수 있는 요소의 시퀀스를 관리할 수 있습니다. 따라서 구현할 수 있는 효율적으로 한 `double-ended queue`합니다. (따라서 이름입니다.)  
  
 아래 설명에 `GValue` 동일 `Value` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Value^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>매개 변수  
 GValue  
 제어 된 시퀀스의 요소는 제네릭 형식입니다.  
  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[deque::const_iterator(STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[deque::const_reference(STL/CLR)](../dotnet/deque-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[deque::const_reverse_iterator(STL/CLR)](../dotnet/deque-const-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[deque::difference_type(STL/CLR)](../dotnet/deque-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[deque::generic_container(STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|  
|[deque::generic_iterator(STL/CLR)](../dotnet/deque-generic-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|  
|[deque::generic_reverse_iterator(STL/CLR)](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반대 반복기의 형식입니다.|  
|[deque::generic_value(STL/CLR)](../dotnet/deque-generic-value-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[deque::iterator(STL/CLR)](../dotnet/deque-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[deque::reference(STL/CLR)](../dotnet/deque-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[deque::reverse_iterator(STL/CLR)](../dotnet/deque-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[deque::size_type(STL/CLR)](../dotnet/deque-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[deque::value_type(STL/CLR)](../dotnet/deque-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[deque::assign(STL/CLR)](../dotnet/deque-assign-stl-clr.md)|모든 요소를 바꿉니다.|  
|[deque::at(STL/CLR)](../dotnet/deque-at-stl-clr.md)|지정된 위치에 있는 요소에 액세스합니다.|  
|[deque::back(STL/CLR)](../dotnet/deque-back-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[deque::begin(STL/CLR)](../dotnet/deque-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[deque::clear(STL/CLR)](../dotnet/deque-clear-stl-clr.md)|모든 요소를 제거합니다.|  
|[deque::deque(STL/CLR)](../dotnet/deque-deque-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[deque::empty(STL/CLR)](../dotnet/deque-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[deque::end(STL/CLR)](../dotnet/deque-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[deque::erase(STL/CLR)](../dotnet/deque-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[deque::front(STL/CLR)](../dotnet/deque-front-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
|[deque::insert(STL/CLR)](../dotnet/deque-insert-stl-clr.md)|지정된 된 위치에 요소를 추가합니다.|  
|[deque::pop_back(STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)|마지막 요소를 제거 합니다.|  
|[deque::pop_front(STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)|첫 번째 요소를 제거합니다.|  
|[deque::push_back(STL/CLR)](../dotnet/deque-push-back-stl-clr.md)|새 마지막 요소를 추가 합니다.|  
|[deque::push_front(STL/CLR)](../dotnet/deque-push-front-stl-clr.md)|새 첫 번째 요소를 추가 합니다.|  
|[deque::rbegin(STL/CLR)](../dotnet/deque-rbegin-stl-clr.md)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[deque::rend(STL/CLR)](../dotnet/deque-rend-stl-clr.md)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[deque::resize(STL/CLR)](../dotnet/deque-resize-stl-clr.md)|요소의 수를 변경합니다.|  
|[deque::size(STL/CLR)](../dotnet/deque-size-stl-clr.md)|요소 수를 계산합니다.|  
|[deque::swap(STL/CLR)](../dotnet/deque-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[deque::to_array(STL/CLR)](../dotnet/deque-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[deque::back_item(STL/CLR)](../dotnet/deque-back-item-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[deque::front_item(STL/CLR)](../dotnet/deque-front-item-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[deque::operator!=(STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)|두 개 결정 `deque` 개체가 같지 않습니다.|  
|[deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)|지정된 위치에 있는 요소에 액세스합니다.|  
|[operator< (deque)(STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)|있는지 여부를 확인 한 `deque` 개체를 사용 하면 다른 노드보다 작은지 `deque` 개체입니다.|  
|[operator<= (deque)(STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|있는지 여부를 확인 한 `deque` 개체 보다 작거나 같으면 다른 `deque` 개체입니다.|  
|[operator= (deque)(STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
|[operator== (deque)(STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)|있는지 여부를 확인 한 `deque` 개체는 다른 `deque` 개체입니다.|  
|[operator> (deque)(STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)|있는지 여부를 확인 한 `deque` 개체가 다른 노드보다 큰지 `deque` 개체입니다.|  
|[operator>= (deque)(STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|있는지 여부를 확인 한 `deque` 개체는 다른 보다 크거나 `deque` 개체입니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스입니다.|  
|<xref:System.Collections.ICollection>|요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IList%601>|형식화 된 요소의 순서가 지정 된 그룹을 유지 합니다.|  
|IDeque < 값\>|제네릭 컨테이너를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 제어 블록을 지정 하는 핸들의 배열을 저장 하는 시퀀스에 대 한 저장소를 해제 `Value` 요소입니다. 배열 요구에 맞게 증가 합니다. 증가 앞에 추가 하거나 새 요소를 추가 비용은 일정 한 시간 및 남은 요소가 없으면 방해를 받지 하는 방식으로 발생 합니다. 일정 한 시간에서 및 나머지 요소를 방해 하지 않고 한쪽 끝에 있는 요소를 제거할 수도 있습니다. 따라서는 q u e는 적합 한 템플릿 클래스에 대 한 기본 컨테이너 [queue (STL/CLR)](../dotnet/queue-stl-clr.md) 또는 템플릿 클래스 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)합니다.  
  
 A `deque` 개체가 첫 번째 (전면) 요소에 대 한 0에서 계산한 직접 숫자의 위치를 지정 하는 요소를 참조할 수 의미 하는 임의 액세스 반복기 지원 [deque:: size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() - 1` 에 대 한 마지막 (뒤로) 요소입니다. 또한는 q u e에 적합 한 템플릿 클래스에 대 한 기본 컨테이너 임을 의미 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)합니다.  
  
 Deque 반복기를 지정 하는 요소에 대 한 바이어스 함께 해당 관련된 e q u e 개체에 대 한 핸들을 저장 합니다. 반복기의 관련된 컨테이너 개체와만 사용할 수 있습니다. Deque 요소의 바이어스는 `not` 같지의 위치입니다. 삽입 하는 첫 번째 요소의 0 바이어스, 다음 추가 된 요소에 1, 바이어스를 갖지만 다음 앞에 추가 요소에는-1 바이어스.  
  
 삽입 또는 양쪽 끝 요소를 지운지 않습니다 `not` 유효한 편향을에 저장 된 요소 값을 변경 합니다. 하지만 삽입 또는 제거 내부 요소 `can` 반복기에서 지정 된 값도 변경할 수 있도록 지정된 바이어스에 저장 된 요소 값을 변경 합니다. (컨테이너 요소를 복사 또는 삽입 하기 전에 구멍을 생성 또는 삭제 한 후 구멍을 채울 아래쪽에 있을 수 있습니다.) 그럼에도 불구 하 고 유효한 요소를 지정 하는 해당 바이어스도 e q u e 반복기 유효 합니다. 또한 유효한 반복기 dereferencable 남아-액세스 또는으로 해당 바이어스에서 반환 된 반복기에 대 한 바이어스 같지 않습니다.-지정 된 요소 값을 변경 하려면 사용할 수 있습니다 `end()`합니다.  
  
 지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 컨테이너를 제거 합니다. 모든 요소를 지웁니다. 따라서 요소 형식이 ref 클래스는 컨테이너 보다 수명이 깁니다 컨테이너 요소가 있는지 확인 합니다. 단, 핸들의 컨테이너 하다 `not` 해당 요소를 제거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/q u e >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)