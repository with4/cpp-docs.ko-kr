---
title: list (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list
dev_langs: C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 40046e2b7263559765c2aab2bef13a17c341f7c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="list-stlclr"></a>list(STL/CLR)
이 템플릿 클래스는 다양 한 길이의 요소 시퀀스를 양방향 액세스할 수 있는 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 여 `list` 하나의 요소 저장 하 고 각 노드 양방향 링크 된 목록으로 요소의 시퀀스를 관리할 수 있습니다.  
  
 아래 설명에 `GValue` 동일 `Value` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Value^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>매개 변수  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[list::const_iterator(STL/CLR)](../dotnet/list-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[list::const_reference(STL/CLR)](../dotnet/list-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[list::const_reverse_iterator(STL/CLR)](../dotnet/list-const-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[list::difference_type(STL/CLR)](../dotnet/list-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[list::generic_container(STL/CLR)](../dotnet/list-generic-container-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|  
|[list::generic_iterator(STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|  
|[list::generic_reverse_iterator(STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반대 반복기의 형식입니다.|  
|[list::generic_value(STL/CLR)](../dotnet/list-generic-value-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[list::iterator(STL/CLR)](../dotnet/list-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[list::reference(STL/CLR)](../dotnet/list-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[list::reverse_iterator(STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[list::size_type(STL/CLR)](../dotnet/list-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[list::value_type(STL/CLR)](../dotnet/list-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[list::assign(STL/CLR)](../dotnet/list-assign-stl-clr.md)|모든 요소를 바꿉니다.|  
|[list::back(STL/CLR)](../dotnet/list-back-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[list::begin(STL/CLR)](../dotnet/list-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[list::clear(STL/CLR)](../dotnet/list-clear-stl-clr.md)|모든 요소를 제거합니다.|  
|[list::empty(STL/CLR)](../dotnet/list-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[list::end(STL/CLR)](../dotnet/list-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[list::erase(STL/CLR)](../dotnet/list-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[list::front(STL/CLR)](../dotnet/list-front-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
|[list::insert(STL/CLR)](../dotnet/list-insert-stl-clr.md)|지정된 된 위치에 요소를 추가합니다.|  
|[list::list(STL/CLR)](../dotnet/list-list-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[list::merge(STL/CLR)](../dotnet/list-merge-stl-clr.md)|제어 된 시퀀스를 정렬 된 두 개의 병합 합니다.|  
|[list::pop_back(STL/CLR)](../dotnet/list-pop-back-stl-clr.md)|마지막 요소를 제거 합니다.|  
|[list::pop_front(STL/CLR)](../dotnet/list-pop-front-stl-clr.md)|첫 번째 요소를 제거합니다.|  
|[list::push_back(STL/CLR)](../dotnet/list-push-back-stl-clr.md)|새 마지막 요소를 추가 합니다.|  
|[list::push_front(STL/CLR)](../dotnet/list-push-front-stl-clr.md)|새 첫 번째 요소를 추가 합니다.|  
|[list::rbegin(STL/CLR)](../dotnet/list-rbegin-stl-clr.md)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[list::remove(STL/CLR)](../dotnet/list-remove-stl-clr.md)|지정된 된 값을 가진 요소를 제거합니다.|  
|[list::remove_if(STL/CLR)](../dotnet/list-remove-if-stl-clr.md)|지정 된 테스트를 통과 하는 요소를 제거 합니다.|  
|[list::rend(STL/CLR)](../dotnet/list-rend-stl-clr.md)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[list::resize(STL/CLR)](../dotnet/list-resize-stl-clr.md)|요소의 수를 변경합니다.|  
|[list::reverse(STL/CLR)](../dotnet/list-reverse-stl-clr.md)|제어 되는 시퀀스를 반대로 바꿉니다.|  
|[list::size(STL/CLR)](../dotnet/list-size-stl-clr.md)|요소 수를 계산합니다.|  
|[list::sort(STL/CLR)](../dotnet/list-sort-stl-clr.md)|제어 된 시퀀스를 정렬 합니다.|  
|[list::splice(STL/CLR)](../dotnet/list-splice-stl-clr.md)|노드 간의 연결을 다시 붙입니다.|  
|[list::swap(STL/CLR)](../dotnet/list-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[list::to_array(STL/CLR)](../dotnet/list-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
|[list::unique(STL/CLR)](../dotnet/list-unique-stl-clr.md)|지정된 테스트를 통과하는 인접 요소를 제거합니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[list::back_item(STL/CLR)](../dotnet/list-back-item-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[list::front_item(STL/CLR)](../dotnet/list-front-item-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[list::operator=(STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
|[operator!= (list)(STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)|있는지 여부를 확인 한 `list` 개체가 다른과 같지 않습니다. `list` 개체입니다.|  
|[operator< (list)(STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)|있는지 여부를 확인 한 `list` 개체를 사용 하면 다른 노드보다 작은지 `list` 개체입니다.|  
|[operator<= (list)(STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)|있는지 여부를 확인 한 `list` 개체 보다 작거나 같으면 다른 `list` 개체입니다.|  
|[operator== (list)(STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)|있는지 여부를 확인 한 `list` 개체는 다른 `list` 개체입니다.|  
|[operator> (list)(STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)|있는지 여부를 확인 한 `list` 개체가 다른 노드보다 큰지 `list` 개체입니다.|  
|[operator>= (list)(STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|있는지 여부를 확인 한 `list` 개체는 다른 보다 크거나 `list` 개체입니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스입니다.|  
|<xref:System.Collections.ICollection>|요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소의 그룹을 유지 합니다.|  
|IList\<값 >|제네릭 컨테이너를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 양방향 링크 목록에 개별 노드로 제어 하는 시퀀스에 대 한 저장소를 해제 합니다. 다른 한 노드의 콘텐츠를 복사 하 여 되지 노드 간의 링크를 변경 하 여 요소를 재정렬 합니다. 즉, 삽입 하 고 나머지 요소를 방해 하지 않고 자유롭게 요소를 제거할 수 있습니다. 따라서 목록을 적합 한 템플릿 클래스에 대 한 기본 컨테이너 [queue (STL/CLR)](../dotnet/queue-stl-clr.md) 또는 템플릿 클래스 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)합니다.  
  
 A `list` 개체가 지원 양방향 반복기를 의미 하는 제어 된 시퀀스의 요소를 지정 하는 반복기를 제공 하는 인접 요소를 한 단계씩 실행할 수 있습니다. 반환 된 반복기에 해당 하는 특수 헤드 노드 [list:: end (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`합니다. 있는 경우이 반복기는 제어 되는 시퀀스에서 마지막 요소를 연결할를 감소 시킬 수 있습니다. 헤드 노드에 도달 하는 목록 반복기를 증가 시킬 수 있습니다 및 같음 비교 다음 `end()`합니다. 반환 된 반복기를 역 참조할 수 없습니다 하지만 `end()`합니다.  
  
 참고 직접 숫자의 위치를 지정 하는 목록 요소를 참조할 수 없습니다-임의 액세스 반복기를 필요로 하 합니다. 목록 이므로 `not` 템플릿 클래스에 대 한 기본 컨테이너로 사용 가능한 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)합니다.  
  
 목록 반복기 해당 연결 된 목록 노드를 차례로 연결 된 컨테이너에 대 한 핸들을 저장 하는 핸들을 저장 합니다. 반복기의 관련된 컨테이너 개체와만 사용할 수 있습니다. 목록 반복기 일부 목록과 연결 된 경우에 연결 된 목록 노드 유효한 상태를 유지 합니다. 유효한 반복기 dereferencable 연결은 액세스 또는 같지 않은 것으로 지정-요소 값을 변경 하려면 사용할 수 또한 `end()`합니다.  
  
 지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 컨테이너를 제거 합니다. 모든 요소를 지웁니다. 따라서 요소 형식이 ref 클래스는 컨테이너 보다 수명이 깁니다 컨테이너 요소가 있는지 확인 합니다. 단, 핸들의 컨테이너 하다 `not` 해당 요소를 제거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)