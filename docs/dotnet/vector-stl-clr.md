---
title: vector (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector
dev_langs:
- C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: de5d09d569933dc06666ed2008081703d59c1564
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="vector-stlclr"></a>vector(STL/CLR)
템플릿 클래스는 임의 액세스를 가진 요소의 다양 한 길이의 시퀀스를 제어 하는 개체를 설명 합니다. 컨테이너를 사용 하 여 `vector` 저장소의 연속 블록으로 요소의 시퀀스를 관리할 수 있습니다. 블록 요구에 맞게 증가 하는 배열을로 구현 됩니다.  
  
 아래 설명에 `GValue` 동일 `Value` 후자 형식인 ref 하지 않는 한 경우에서 이기 `Value^`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>매개 변수  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[vector::const_iterator(STL/CLR)](../dotnet/vector-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[vector::const_reference(STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[vector::const_reverse_iterator(STL/CLR)](../dotnet/vector-const-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[vector::difference_type(STL/CLR)](../dotnet/vector-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[vector::generic_container(STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|  
|[vector::generic_iterator(STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|  
|[vector::generic_reverse_iterator(STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반대 반복기의 형식입니다.|  
|[vector::generic_value(STL/CLR)](../dotnet/vector-generic-value-stl-clr.md)|컨테이너에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[vector::iterator(STL/CLR)](../dotnet/vector-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[vector::reference(STL/CLR)](../dotnet/vector-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[vector::reverse_iterator(STL/CLR)](../dotnet/vector-reverse-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[vector::size_type(STL/CLR)](../dotnet/vector-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[vector::value_type(STL/CLR)](../dotnet/vector-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[vector::assign(STL/CLR)](../dotnet/vector-assign-stl-clr.md)|모든 요소를 바꿉니다.|  
|[vector::at(STL/CLR)](../dotnet/vector-at-stl-clr.md)|지정된 위치에 있는 요소에 액세스합니다.|  
|[vector::back(STL/CLR)](../dotnet/vector-back-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[vector::begin(STL/CLR)](../dotnet/vector-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[vector::capacity(STL/CLR)](../dotnet/vector-capacity-stl-clr.md)|컨테이너에 할당 된 저장소의 크기를 보고합니다.|  
|[vector::clear(STL/CLR)](../dotnet/vector-clear-stl-clr.md)|모든 요소를 제거합니다.|  
|[vector::empty(STL/CLR)](../dotnet/vector-empty-stl-clr.md)|요소가 있는지 여부를 테스트합니다.|  
|[vector::end(STL/CLR)](../dotnet/vector-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[vector::erase(STL/CLR)](../dotnet/vector-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[vector::front(STL/CLR)](../dotnet/vector-front-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
|[vector::insert(STL/CLR)](../dotnet/vector-insert-stl-clr.md)|지정된 된 위치에 요소를 추가합니다.|  
|[vector::pop_back(STL/CLR)](../dotnet/vector-pop-back-stl-clr.md)|마지막 요소를 제거 합니다.|  
|[vector::push_back(STL/CLR)](../dotnet/vector-push-back-stl-clr.md)|새 마지막 요소를 추가 합니다.|  
|[vector::rbegin(STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[vector::rend(STL/CLR)](../dotnet/vector-rend-stl-clr.md)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[vector::reserve(STL/CLR)](../dotnet/vector-reserve-stl-clr.md)|컨테이너에 대 한 최소 증가 용량을 보장합니다.|  
|[vector::resize(STL/CLR)](../dotnet/vector-resize-stl-clr.md)|요소의 수를 변경합니다.|  
|[vector::size(STL/CLR)](../dotnet/vector-size-stl-clr.md)|요소 수를 계산합니다.|  
|[vector::swap(STL/CLR)](../dotnet/vector-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[vector::to_array(STL/CLR)](../dotnet/vector-to-array-stl-clr.md)|제어 되는 새 배열에 복사합니다.|  
|[vector::vector(STL/CLR)](../dotnet/vector-vector-stl-clr.md)|컨테이너 개체를 만듭니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[vector::back_item(STL/CLR)](../dotnet/vector-back-item-stl-clr.md)|마지막 요소에 액세스합니다.|  
|[vector::front_item(STL/CLR)](../dotnet/vector-front-item-stl-clr.md)|첫 번째 요소에 액세스합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[vector::operator=(STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)|제어되는 시퀀스를 바꿉니다.|  
|[vector::operator(STL/CLR)](../dotnet/vector-operator-stl-clr.md)|지정된 위치에 있는 요소에 액세스합니다.|  
|[operator!= (vector)(STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)|있는지 여부를 확인 한 `vector` 개체가 다른과 같지 않습니다. `vector` 개체입니다.|  
|[operator< (vector)(STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)|있는지 여부를 확인 한 `vector` 개체를 사용 하면 다른 노드보다 작은지 `vector` 개체입니다.|  
|[operator<= (vector)(STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|있는지 여부를 확인 한 `vector` 개체 보다 작거나 같으면 다른 `vector` 개체입니다.|  
|[operator== (vector)(STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)|있는지 여부를 확인 한 `vector` 개체는 다른 `vector` 개체입니다.|  
|[operator> (vector)(STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)|있는지 여부를 확인 한 `vector` 개체가 다른 노드보다 큰지 `vector` 개체입니다.|  
|[operator>= (vector)(STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|있는지 여부를 확인 한 `vector` 개체는 다른 보다 크거나 `vector` 개체입니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.ICloneable>|개체를 복제 합니다.|  
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스입니다.|  
|<xref:System.Collections.ICollection>|요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|형식화 된 요소 시퀀스입니다.|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소의 그룹을 유지 합니다.|  
|<xref:System.Collections.Generic.IList%601>|형식화 된 요소의 순서가 지정 된 그룹을 유지 합니다.|  
|IVector < 값\>|제네릭 컨테이너를 유지 합니다.|  
  
## <a name="remarks"></a>설명  
 개체 할당 및 제어의 배열을 저장 하는 시퀀스에 대 한 저장소를 해제 `Value` 요구에 맞게 증가 하는 요소입니다. 증가 하는 새 요소를 추가 비용이 분할 상환된 상수 시간 하는 방식으로 발생 합니다. 즉, 끝에 요소를 추가 하는 비용 증가 하지 않습니다, 평균적으로 더 큰 제어 되는 시퀀스 가져옵니다의 길이로 합니다. 따라서 벡터는 적합 한 템플릿 클래스에 대 한 기본 컨테이너 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)합니다.  
  
 A `vector` 즉, 첫 번째 (앞) 요소에 대 한 0에서 계산한 직접 숫자의 위치를 지정 하는 요소를 참조할 수는 지원 임의 액세스 반복기 `size() - 1` 마지막 (뒤로) 요소에 대 한 합니다. 또한 벡터에 적합 한 템플릿 클래스에 대 한 기본 컨테이너 임을 의미 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)합니다.  
  
 벡터 반복기를 지정 하는 요소에 대 한 바이어스 함께 해당 관련된 벡터 개체에 대 한 핸들을 저장 합니다. 반복기의 관련된 컨테이너 개체와만 사용할 수 있습니다. 벡터 요소의 바이어스의 위치와 같습니다.  
  
 삽입 또는 요소를 지운 반복기에서 지정 된 값도 변경할 수 있도록 지정된 된 위치에 저장 된 요소 값을 변경할 수 있습니다. (컨테이너 요소를 복사 또는 삽입 하기 전에 구멍을 생성 또는 삭제 한 후 구멍을 채울 아래쪽에 있을 수 있습니다.) 그럼에도 불구 하 고 벡터 반복기 유효 범위에 경우에 바이어스 `[0, size()]`합니다. 또한 유효한 반복기 dereferencable 남아-액세스 하거나 해당 바이어스과 같지 않은으로 지정-요소 값을 변경 하는 사용할 수 있습니다 `size()`합니다.  
  
 지우거 나 요소를 제거 합니다. 저장된 된 값에 대 한 소멸자를 호출 합니다. 컨테이너를 제거 합니다. 모든 요소를 지웁니다. 따라서 요소 형식이 ref 클래스는 컨테이너 보다 수명이 깁니다 컨테이너 요소가 있는지 확인 합니다. 단, 컨테이너 핸들의 해당 요소를 제거 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [list (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [stack (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector::size(STL/CLR)](../dotnet/vector-size-stl-clr.md)  
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)