---
title: list (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list
- cliext::list::assign
- cliext::list::assign
- cliext::list::back
- cliext::list::back_item
- cliext::list::begin
- cliext::list::clear
- cliext::list::const_iterator
- cliext::list::const_reference
- cliext::list::const_reverse_iterator
- cliext::list::difference_type
- cliext::list::empty
- cliext::list::end
- cliext::list::erase
- cliext::list::front
- cliext::list::front_item
- cliext::list::generic_container
- cliext::list::generic_iterator
- cliext::list::generic_reverse_iterator
- cliext::list::generic_value
- cliext::list::insert
- cliext::list::iterator
- cliext::list::list
- cliext::list::merge
- cliext::list::operator=
- cliext::list::pop_back
- cliext::list::pop_front
- cliext::list::push_back
- cliext::list::push_front
- cliext::list::rbegin
- cliext::list::reference
- cliext::list::remove
- cliext::list::remove_if
- cliext::list::rend
- cliext::list::resize
- cliext::list::reverse
- cliext::list::reverse_iterator
- cliext::list::size
- cliext::list::size_type
- cliext::list::sort
- cliext::list::splice
- cliext::list::swap
- cliext::list::to_array
- cliext::list::unique
- cliext::list::value_type
- cliext::operator!=(list)
- cliext::operator<(list)
- cliext::operator<=(list)
- cliext::operator==(list)
- cliext::operator>(list)
- cliext::operator>=(list)
dev_langs:
- C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- list member [STL/CLR]
- merge member [STL/CLR]
- operator= member [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- remove member [STL/CLR]
- remove_if member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- sort member [STL/CLR]
- splice member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- unique member [STL/CLR]
- value_type member [STL/CLR]
- operator!=(list) member [STL/CLR]
- operator<(list) member [STL/CLR]
- operator<=(list) member [STL/CLR]
- operator==(list) member [STL/CLR]
- operator>(list) member [STL/CLR]
- operator>=(list) member [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4e6ae13efabd34c6c685b07691789634ca0aed9c
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305919"
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
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/목록 >  
  
 **Namespace:** cliext 

## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[list::const_iterator(STL/CLR)](#const_iterator)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[list::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|  
|[list::const_reverse_iterator(STL/CLR)](#const_reverse_iterator)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|  
|[list::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[list::generic_container(STL/CLR)](#generic_container)|컨테이너에 대 한 제네릭 인터페이스의 형식입니다.|  
|[list::generic_iterator(STL/CLR)](#generic_iterator)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반복기의 형식입니다.|  
|[list::generic_reverse_iterator(STL/CLR)](#generic_reverse_iterator)|컨테이너에 대 한 제네릭 인터페이스에 대 한 반대 반복기의 형식입니다.|  
|[list::generic_value(STL/CLR)](#generic_value)|컨테이너에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|  
|[list::iterator(STL/CLR)](#iterator)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[list::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|  
|[list::reverse_iterator(STL/CLR)](#reverse_iterator)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|  
|[list::size_type(STL/CLR)](#size_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[list::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[list::assign(STL/CLR)](#assign)|모든 요소를 바꿉니다.|  
|[list::back(STL/CLR)](#back)|마지막 요소에 액세스합니다.|  
|[list::begin(STL/CLR)](#begin)|제어되는 시퀀스의 시작을 지정합니다.|  
|[list::clear(STL/CLR)](#clear)|모든 요소를 제거합니다.|  
|[list::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|  
|[list::end(STL/CLR)](#end)|제어되는 시퀀스의 끝을 지정합니다.|  
|[list::erase(STL/CLR)](#erase)|지정된 위치에 있는 요소를 제거합니다.|  
|[list::front(STL/CLR)](#front)|첫 번째 요소에 액세스합니다.|  
|[list::insert(STL/CLR)](#insert)|지정된 된 위치에 요소를 추가합니다.|  
|[list::list(STL/CLR)](#list)|컨테이너 개체를 만듭니다.|  
|[list::merge(STL/CLR)](#merge)|제어 된 시퀀스를 정렬 된 두 개의 병합 합니다.|  
|[list::pop_back(STL/CLR)](#pop_back)|마지막 요소를 제거 합니다.|  
|[list::pop_front(STL/CLR)](#pop_front)|첫 번째 요소를 제거합니다.|  
|[list::push_back(STL/CLR)](#push_back)|새 마지막 요소를 추가 합니다.|  
|[list::push_front(STL/CLR)](#push_front)|새 첫 번째 요소를 추가 합니다.|  
|[list::rbegin(STL/CLR)](#rbegin)|제어되는 역방향 시퀀스의 시작을 지정합니다.|  
|[list::remove(STL/CLR)](#remove)|지정된 된 값을 가진 요소를 제거합니다.|  
|[list::remove_if(STL/CLR)](#remove_if)|지정 된 테스트를 통과 하는 요소를 제거 합니다.|  
|[list::rend(STL/CLR)](#rend)|제어되는 역방향 시퀀스의 끝을 지정합니다.|  
|[list::resize(STL/CLR)](#resize)|요소의 수를 변경합니다.|  
|[list::reverse(STL/CLR)](#reverse)|제어 되는 시퀀스를 반대로 바꿉니다.|  
|[list::size(STL/CLR)](#size)|요소 수를 계산합니다.|  
|[list::sort(STL/CLR)](#sort)|제어 된 시퀀스를 정렬 합니다.|  
|[list::splice(STL/CLR)](#splice)|노드 간의 연결을 다시 붙입니다.|  
|[list::swap(STL/CLR)](#swap)|두 컨테이너의 내용을 바꿉니다.|  
|[list::to_array(STL/CLR)](#to_array)|제어 되는 새 배열에 복사합니다.|  
|[list::unique(STL/CLR)](#unique)|지정된 테스트를 통과하는 인접 요소를 제거합니다.|  
  
|속성|설명|  
|--------------|-----------------|  
|[list::back_item(STL/CLR)](#back_item)|마지막 요소에 액세스합니다.|  
|[list::front_item(STL/CLR)](#front_item)|첫 번째 요소에 액세스합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[list::operator=(STL/CLR)](#op_as)|제어되는 시퀀스를 바꿉니다.|  
|[operator!= (list)(STL/CLR)](#op_neq)|있는지 여부를 확인 한 `list` 개체가 다른과 같지 않습니다. `list` 개체입니다.|  
|[operator< (list)(STL/CLR)](#op_lt)|있는지 여부를 확인 한 `list` 개체를 사용 하면 다른 노드보다 작은지 `list` 개체입니다.|  
|[operator<= (list)(STL/CLR)](#op_lteq)|있는지 여부를 확인 한 `list` 개체 보다 작거나 같으면 다른 `list` 개체입니다.|  
|[operator== (list)(STL/CLR)](#op_eq)|있는지 여부를 확인 한 `list` 개체는 다른 `list` 개체입니다.|  
|[operator> (list)(STL/CLR)](#op_gt)|있는지 여부를 확인 한 `list` 개체가 다른 노드보다 큰지 `list` 개체입니다.|  
|[operator>= (list)(STL/CLR)](#op_gteq)|있는지 여부를 확인 한 `list` 개체는 다른 보다 크거나 `list` 개체입니다.|  
  
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
  
## <a name="assign"></a> list:: assign (STL/CLR)
모든 요소를 바꿉니다.  
  
### <a name="syntax"></a>구문  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 count  
 삽입할 요소의 수입니다.  
  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 오른쪽  
 삽입 하는 열거형입니다.  
  
 val  
 삽입할 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 반복 된 제어 되는 시퀀스 바꿉니다 `count` 값의 요소 `val`합니다. 하면을 채우는 데 사용할 컨테이너 요소와 동일한 값이 모두 포함 합니다.  
  
 경우 `InIt` 정수 형식, 두 번째 멤버 함수는 동일 하 게 동작 `assign((size_type)first, (value_type)last)`합니다. 제어 되는 순서와 대체 그렇지 않으면 [`first`, `last`). 사용할 있습니다 제어 된 시퀀스 복사본 되도록 다른 시퀀스.  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 대체 하는 세 번째 멤버 함수 `right`합니다. 제어 되는 시퀀스의 사본을 열거형에서 설명 하는 순서를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_assign.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    cliext::list<wchar_t>::iterator it = c1.end();   
    c2.assign(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
 
## <a name="back"></a> list:: back (STL/CLR)
마지막 요소에 액세스합니다.  
  
### <a name="syntax"></a>구문  
  
```  
reference back();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 비어 있어야 하는 제어 된 시퀀스의 마지막 요소에 대 한 참조를 반환 합니다. 존재 하는 것을 알고 있는 경우 마지막 요소를 액세스 하려면 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  

## <a name="back_item"></a> list:: back_item (STL/CLR)
마지막 요소에 액세스합니다.  
  
### <a name="syntax"></a>구문  
  
```  
property value_type back_item;  
```  
  
### <a name="remarks"></a>설명  
 비어 있는 제어 된 시퀀스의 마지막 요소를 액세스 하는 속성입니다. 읽기 또는 존재 하는 것을 알고 있는 경우 마지막 요소를 쓰기 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_back_item.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  

## <a name="begin"></a> list:: begin (STL/CLR)
제어되는 시퀀스의 시작을 지정합니다.  
  
### <a name="syntax"></a>구문  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스 또는 빈 시퀀스의 끝 바로 다음 첫 번째 요소를 지정 하는 임의 액세스 반복기를 반환 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스의 길이가 변경 하는 경우의 상태 제어 된 시퀀스의 시작 부분을 변경할 수 있습니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_begin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  

## <a name="clear"></a> list:: clear (STL/CLR)
모든 요소를 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수 시그니처 [list:: erase (STL/CLR)](../dotnet/list-erase-stl-clr.md) `(` [list:: begin (STL/CLR)](../dotnet/list-begin-stl-clr.md) `(),` [list:: end (STL/CLR)](../dotnet/list-end-stl-clr.md) `())`. 제어 되는 시퀀스 비어 있는지 확인 하려면 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_clear.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  

## <a name="const_iterator"></a> list:: const_iterator (STL/CLR)
제어되는 시퀀스에 대한 상수 반복기의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 지정 되지 않은 형식의 개체를 설명 `T2` 제어 되는 시퀀스에 대 한 상수 임의 액세스 반복기로 사용할 수 있는 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_const_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::list<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> list:: const_reference (STL/CLR)
요소에 대한 상수 참조의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 요소에 대 한 상수 참조를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_const_reference.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::list<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::list<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reverse_iterator"></a> list:: const_reverse_iterator (STL/CLR)
제어 되는 시퀀스에 대 한 상수 역방향 반복기의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 지정 되지 않은 형식의 개체를 설명 `T4` 제어 되는 시퀀스에 대 한 상수 역방향 반복기로 사용할 수 있는 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="difference_type"></a> list:: difference_type (STL/CLR)
두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은 부호 있는 요소 수를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp 
// cliext_list_difference_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::list<wchar_t>::difference_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  

## <a name="empty"></a> list:: empty (STL/CLR)
요소가 있는지 여부를 테스트합니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 동일 [list:: size (STL/CLR)](../dotnet/list-size-stl-clr.md)`() == 0`합니다. 목록이 비어 있는지 여부를 테스트 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_empty.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  

## <a name="end"></a> list:: end (STL/CLR)
제어되는 시퀀스의 끝을 지정합니다.  
  
### <a name="syntax"></a>구문  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어 된 시퀀스의 끝 바로 다음을 가리키는 임의 액세스 반복기를 반환합니다. 제어 된 시퀀스의 끝을 지정 하는 반복기를 가져올 사용 해당 상태 대상이 제어 된 시퀀스의 길이가 변경 하는 경우 변경 되지 않습니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_end.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::list<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  

## <a name="erase"></a> list:: erase (STL/CLR)
지정된 위치에 있는 요소를 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 범위를 지우려면의 시작입니다.  
  
 last  
 범위를 지우려면의 끝입니다.  
  
 형식에 대한 설명  
 지울 요소입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 `where`로 지정된 제어 시퀀스의 요소를 제거합니다. 단일 요소를 제거 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 0 개 이상의 연속 요소를 제거 하려면 사용 합니다.  
  
 제거 된 요소 뒤에 남은 첫 번째 요소를 지정 하는 반복기를 반환 하는 두 멤버 함수 또는 [list:: end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()` 이러한 요소가 없을 경우.  
  
 요소를 지운 경우에 요소 복사본의 수는 시퀀스의 할수록 끝과 여 지우기의 끝 간 요소 수에 비례 합니다. (시퀀스의 끝에 하나 이상의 요소를 지우는 중 요소 복사본이 발생 합니다.)  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_erase.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  

## <a name="front"></a> list:: front (STL/CLR)
첫 번째 요소에 액세스합니다.  
  
### <a name="syntax"></a>구문  
  
```  
reference front();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 비어 있어야 하는 제어 된 시퀀스의 첫 번째 요소에 대 한 참조를 반환 합니다. 읽기 또는 존재 하는 것을 알고 있는 경우 첫 번째 요소를 쓰기를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  

## <a name="front_item"></a> list:: front_item (STL/CLR)
첫 번째 요소에 액세스합니다.  
  
### <a name="syntax"></a>구문  
  
```  
property value_type front_item;  
```  
  
### <a name="remarks"></a>설명  
 비어 있는 제어 된 시퀀스의 첫 번째 요소를 액세스 하는 속성입니다. 읽기 또는 존재 하는 것을 알고 있는 경우 첫 번째 요소를 쓰기를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_front_item.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  

## <a name="generic_container"></a> list:: generic_container (STL/CLR)
컨테이너에 대 한 제네릭 인터페이스의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IList<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_generic_container.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(gc1->end(), L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push_back(L'e');   
  
    System::Collections::IEnumerator^ enum1 =   
        gc1->GetEnumerator();   
    while (enum1->MoveNext())   
        System::Console::Write(" {0}", enum1->Current);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  

## <a name="generic_iterator"></a> list:: generic_iterator (STL/CLR)
컨테이너에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 반복기의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식은이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스와 함께 사용할 수 있는 일반 반복기를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="generic_reverse_iterator"></a> list:: generic_reverse_iterator (STL/CLR)
컨테이너에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 한 반대 반복기의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 형식은이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스와 함께 사용할 수 있는 제네릭 역방향 반복기를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a c c  
```  

## <a name="generic_value"></a> list:: generic_value (STL/CLR)
컨테이너에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 요소의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 형식의 개체를 설명 `GValue` 이 서식 파일 컨테이너 클래스에 대 한 제네릭 인터페이스와 함께 사용 하기 위해 저장 된 요소 값을 설명 하는 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_generic_value.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="insert"></a> list:: insert (STL/CLR)
지정된 된 위치에 요소를 추가합니다.  
  
### <a name="syntax"></a>구문  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 count  
 삽입할 요소의 수입니다.  
  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 오른쪽  
 삽입 하는 열거형입니다.  
  
 val  
 삽입할 요소의 값입니다.  
  
 형식에 대한 설명  
 앞에 삽입 하는 컨테이너의 위치입니다.  
  
### <a name="remarks"></a>설명  
 가 가리키는 요소 앞의 삽입, 함수는 멤버의 각 `where` 제어 된 시퀀스의 시퀀스는 나머지 피연산자에서 지정 합니다.  
  
 첫 번째 멤버 함수는 값을 가진 요소를 삽입 `val` 새로 삽입된 된 요소를 지정 하는 반복기를 반환 합니다. 반복기에서 지정 하는 장소 하기 전에 단일 요소를 삽입 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 `val` 값의 `count` 요소 반복을 삽입합니다. 같은 값의 모든 복사본 인 0 개 이상의 연속 요소를 삽입 하려면 사용 합니다.  
  
 `InIt`가 정수 형식이면 세 번째 멤버 함수는 `insert(where, (size_type)first, (value_type)last)`와 동일하게 동작합니다. 시퀀스를 삽입, 그렇지 않으면 [`first`, `last`). 다른 시퀀스에서 복사 된 0 개 이상의 연속 요소를 삽입 하려면 사용 합니다.  
  
 로 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 `right`합니다. 열거자에서 설명 하는 시퀀스를 삽입 하려면 사용 합니다.  
  
 단일 요소를 삽입할 경우에 요소 복사본의 수는 삽입 지점와 떨어진 끝 시퀀스의 요소 수에 비례 합니다. (시퀀스의 끝에 하나 이상의 요소를 삽입할 경우 요소 복사본이 발생 합니다.) 경우 `InIt` 입력 반복기, 세 번째 멤버 함수는 시퀀스의 각 요소에 대 한 단일 삽입을 효과적으로 수행 합니다. 삽입할 때 그렇지 `N` 요소, 요소 복사본 수에 비례는 `N` 삽입 포인터와 떨어진 시퀀스의 끝 간 요소 수를 더한 값입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_insert.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  

## <a name="iterator"></a> list:: iterator (STL/CLR)
제어되는 시퀀스에 대한 반복기의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 지정 되지 않은 형식의 개체를 설명 `T1` 제어 되는 시퀀스에 대 한 임의 액세스 반복기로 사용할 수 있는 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x b c  
```  

## <a name="list"></a> list:: list (STL/CLR)
컨테이너 개체를 만듭니다.  
  
### <a name="syntax"></a>구문  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `count`  
 삽입할 요소의 수입니다.  
  
 `first`  
 삽입할 범위의의 시작입니다.  
  
 `last`  
 삽입할 범위의 끝입니다.  
  
 `right`  
 삽입할 개체 또는 범위입니다.  
  
 `val`  
 삽입할 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
  
 생성자:  
  
 `list();`  
  
 요소가 없는 제어 되는 시퀀스를 초기화합니다. 초기는 빈 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `list(list<Value>% right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right.begin()`, `right.end()`). 목록 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다.  
  
 생성자:  
  
 `list(list<Value>^ right);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`right->begin()`, `right->end()`). 핸들은 목록 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`합니다.  
  
 생성자:  
  
 `explicit list(size_type count);`  
  
 이 있는 제어 된 시퀀스를 초기화 `count` 각 요소 값을 가진 `value_type()`합니다. 있습니다을 채우는 데 사용할 컨테이너 요소와 모든 기본 값이 포함 됩니다.  
  
 생성자:  
  
 `list(size_type count, value_type val);`  
  
 이 있는 제어 된 시퀀스를 초기화 `count` 각 요소 값을 가진 `val`합니다. 하면을 채우는 데 사용할 컨테이너 요소와 동일한 값이 모두 포함 합니다.  
  
 생성자:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 순서와 제어 된 시퀀스를 초기화 합니다. [`first`, `last`). 제어 되는 시퀀스의 사본을 다른 시퀀스를 사용 합니다.  
  
 생성자:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 열거자에 지정 된 시퀀스와 제어 된 시퀀스를 초기화 `right`합니다. 제어 되는 시퀀스의 사본을 열거자에서 설명 하는 다른 시퀀스를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="merge"></a> list:: merge (STL/CLR)
제어 된 시퀀스를 정렬 된 두 개의 병합 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 요소 쌍에 대 한 비교자입니다.  
  
 오른쪽  
 컨테이너에서의 merge입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수에 의해 제어 되는 시퀀스에서 요소를 모두 제거 `right` 제어 되는 시퀀스에 삽입 합니다. 두 시퀀스에서 이전에 정렬 되어야 합니다 `operator<` -시퀀스를 진행 하면서 요소 값에서 감소 하지 해야 합니다. 결과 시퀀스로 정렬 `operator<`합니다. 이 멤버 함수를 사용 하 여 값에도 증가 하는 시퀀스에 값이 증가 하는 두 개의 시퀀스를 병합 합니다.  
  
 두 번째 멤버 함수는 동일 하 게 동작 첫 번째 시퀀스의 기준으로 정렬 된 한다는 점을 제외 하면 `pred`  --  `pred(X, Y)` 모든 요소에 대해 false 이어야 합니다 `X` 요소 다음에 오는 `Y` 시퀀스에서 합니다. 병합 조건자 함수 또는 사용자가 지정한 대리자에 의해 정렬 된 두 개의 시퀀스를 사용 합니다.  
  
 모두 안정적인 병합을 수행 하는 함수에 결과 제어 된 시퀀스에서 원래 제어 된 시퀀스 중 하나에 있는 요소의 없는 쌍 속도가 반대로 바뀝니다. 또한 경우 요소의 쌍 `X` 및 `Y` 순서 지정이 동일할-결과 제어 되는 시퀀스에 `!(X < Y) && !(X < Y)` -제어 되는 원래 시퀀스에서 요소 에의해제어되는시퀀스에서요소앞에표시되`right`.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  

## <a name="op_as"></a> list:: operator = (STL/CLR)
제어되는 시퀀스를 바꿉니다.  
  
### <a name="syntax"></a>구문  
  
```  
list<Value>% operator=(list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 오른쪽  
 복사할 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자 복사본 `right` 개체에 반환 `*this`합니다. 이를 사용하여 제어되는 시퀀스를 `right`의 제어되는 시퀀스 복사본으로 대체합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_as.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="pop_back"></a> list:: pop_back (STL/CLR)
마지막 요소를 제거 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void pop_back();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 비어 있어야 하는 제어 된 시퀀스의 마지막 요소를 제거 합니다. 보다 목록을를 뒤에 한 요소를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_pop_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  

## <a name="pop_front"></a> list:: pop_front (STL/CLR)
첫 번째 요소를 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void pop_front();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 비어 있어야 하는 제어 된 시퀀스의 첫 번째 요소를 제거 합니다. 보다 목록을를 앞에 한 요소를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_pop_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
b c  
```  

## <a name="push_back"></a> list:: push_back (STL/CLR)
새 마지막 요소를 추가 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 값을 가진 요소를 삽입 `val` 제어 된 시퀀스의 끝입니다. 목록에 다른 요소를 추가 하려면 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_push_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="push_front"></a> list:: push_front (STL/CLR)
새 첫 번째 요소를 추가 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void push_front(value_type val);  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 값을 가진 요소를 삽입 `val` 제어 된 시퀀스의 시작 부분에 있습니다. 목록에 다른 요소 앞에 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_push_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="rbegin"></a> list:: rbegin (STL/CLR)
제어되는 역방향 시퀀스의 시작을 지정합니다.  
  
### <a name="syntax"></a>구문  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 빈 시퀀스의 시작 부분 바로 다음 또는 제어 된 시퀀스의 마지막 요소를 지정 하는 역방향 반복기를 반환 합니다. 따라서을 지정 된 `beginning` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 하지만 해당 상태의 시작 부분 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_rbegin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  

## <a name="reference"></a> list:: reference (STL/CLR)
요소에 대한 참조의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 요소에 대 한 참조를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_reference.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::list<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::list<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
A B C  
```  

## <a name="remove"></a> list:: remove (STL/CLR)
지정된 된 값을 가진 요소를 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void remove(value_type val);  
```  
  
#### <a name="parameters"></a>매개 변수  
 val  
 제거할 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는에 대 한 제어 된 시퀀스의 요소를 제거 `((System::Object^)val)->Equals((System::Object^)x)` 가 true (있는 경우). 지정 된 값이 임의의 요소를 지울 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_remove.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove(L'A');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();  
  
// remove and redisplay   
    c1.remove(L'b');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a c  
```  

## <a name="remove_if"></a> list:: remove_if (STL/CLR)
지정 된 테스트를 통과 하는 요소를 제거 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Pred1>  
    void remove_if(Pred1 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 제거할 요소에 대 한 테스트 합니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어 된 시퀀스 (지우기로 적용)에서 제거 모든 요소가 `X` 를 `pred(X)` 그렇습니다. 함수 또는 대리자도 지정 하는 조건을 만족 하는 모든 요소를 제거 하려면 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_remove_if.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b b b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(   
        cliext::equal_to<wchar_t>(), L'd'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(   
        cliext::not_equal_to<wchar_t>(), L'b'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b b b c  
a b b b c  
b b b  
``` 

## <a name="rend"></a> list:: rend (STL/CLR)
제어되는 역방향 시퀀스의 끝을 지정합니다.  
  
### <a name="syntax"></a>구문  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어 된 시퀀스의 시작 부분 바로 다음 가리키는 역방향 반복기를 반환합니다. 따라서을 지정 된 `end` 역방향 시퀀스의 합니다. 지정 하는 반복기를 사용 하면는 `current` 제어 된 시퀀스를 역순으로 표시 하지만 해당 상태의 끝 제어 된 시퀀스의 길이가 변경 되 면 변경할 수 있습니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_rend.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  

## <a name="resize"></a> list:: resize (STL/CLR)
요소의 수를 변경합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>매개 변수  
 new_size  
 제어 된 시퀀스의 새 크기입니다.  
  
 val  
 안쪽 여백 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 두 멤버 함수를 확인 하는 [list:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `()` 예측이 반환 `new_size`합니다. 제어되는 시퀀스 길이를 늘려야 할 경우 첫 번째 멤버 함수는 값이 `value_type()`인 요소를 추가하지만, 두 번째 멤버 함수는 값이 `val`인 요소를 추가합니다. 더 짧은 제어 되는 시퀀스를 두 멤버 함수는 효과적으로 지울 마지막 요소 [list:: size (STL/CLR)](../dotnet/list-size-stl-clr.md) `() -` `new_size` 시간입니다. 제어 되는 시퀀스의 크기가을 사용 하면 `new_size`, 트리밍 하거나 현재 제어 되는 시퀀스를 패딩 하 여 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  

## <a name="reverse"></a> list:: reverse (STL/CLR)
제어 되는 시퀀스를 반대로 바꿉니다.  
  
### <a name="syntax"></a>구문  
  
```  
void reverse();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스에 있는 모든 요소의 순서를 반대로 바꿉니다. 요소 목록이 반영 하기 위해 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_reverse.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// reverse and redisplay   
    c1.reverse();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
```  

## <a name="reverse_iterator"></a> list:: reverse_iterator (STL/CLR)
제어되는 시퀀스에 대한 반대 반복기의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 제어된 시퀀스에 대해 반대 반복기로 사용될 수 있는 지정되지 않은 `T3` 형식의 개체를 설명합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
x b a  
```  
  
## <a name="size"></a> list:: size (STL/CLR)
요소 수를 계산합니다.  
  
### <a name="syntax"></a>구문  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 제어 되는 시퀀스의 현재 요소 수를 확인 하려면 사용 합니다. 모든 경우에 중요 한 여부 시퀀스 크기가 0이 아닌 참조 [list:: empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)`()`합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_size.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  

## <a name="size_type"></a> list:: size_type (STL/CLR)
두 요소 사이의 부호가 있는 거리의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>설명  
 형식은은 음수가 아닌 요소 수를 설명 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_size_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::list<wchar_t>::size_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```

## <a name="sort"></a> list:: sort (STL/CLR)
제어 된 시퀀스를 정렬 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 요소 쌍에 대 한 비교자입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수 다시 제어 된 시퀀스의 요소 정렬로 정렬 됩니다 있는 `operator<` -시퀀스를 진행 하면서 값 요소 줄어들지 않습니다. 이 멤버 함수를 사용 하 여 오름차순으로 정렬 순서를 정렬 합니다.  
  
 두 번째 멤버 함수는 동일 하 게 동작 첫 번째 시퀀스는 기준으로 정렬 한다는 점을 제외 하면 `pred`  --  `pred(X, Y)` 모든 요소에 대해 false가 `X` 요소 다음에 오는 `Y` 결과 시퀀스에서 합니다. 조건자 함수 또는 대리자에 의해 지정 된 순서에 따라 시퀀스를 정렬 하려면 사용 합니다.  
  
 모두 안정적인 정렬 수행 하는 기능이-결과 제어 된 시퀀스에서 제어 되는 원래 시퀀스의 요소 쌍 없는 속도가 반대로 바뀝니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_sort.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
a b c  
``` 

## <a name="splice"></a> list:: splice (STL/CLR)
노드 간 링크 restitch 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>매개 변수  
 첫 번째  
 결합할 범위의 시작입니다.  
  
 last  
 결합할 범위의 끝입니다.  
  
 오른쪽  
 컨테이너에서 splice입니다.  
  
 형식에 대한 설명  
 Splice 전에 컨테이너에서 위치입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수에 의해 제어 시퀀스를 삽입 `right` 가리키는 제어 된 시퀀스의 요소 앞 `where`합니다. 또한 `right`에서 모든 요소를 제거합니다. (`%right` 같지 않아야 `this`.) 다른 파티션으로 splice 모두 하나의 목록에 사용 합니다.  
  
 가 가리키는 요소를 제거 하는 두 번째 멤버 함수 `first` 에서 제어 시퀀스의 `right` 가리키는 제어 된 시퀀스의 요소 앞에 삽입 `where`합니다. (경우 `where` `==` `first` `||` `where` `== ++first`, 변경 되지 않습니다.) 다른 파티션으로 하나의 목록의 단일 요소를 결합할 사용할 수 있습니다.  
  
 세 번째 멤버 함수에 지정 된 하위 범위를 삽입 [`first`, `last`)으로 제어 되는 시퀀스에서 `right` 가리키는 제어 된 시퀀스의 요소 앞 `where`합니다. 또한 `right`로 제어되는 시퀀스에서 원래 하위 범위를 제거합니다. (If `right` `==` `this`, 범위 [`first`, `last`)로 가리키는 요소를 포함 하지 않아야 `where`.) Splice 다른 파티션으로 한 목록에서 0 개 이상의 요소는 하위 시퀀스를 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp
// cliext_list_splice.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```    

## <a name="swap"></a> list:: swap (STL/CLR)
두 컨테이너의 내용을 바꿉니다.  
  
### <a name="syntax"></a>구문  
  
```  
void swap(list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 오른쪽  
 콘텐츠와 바꿀 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 `*this` 와 `right`간에 제어되는 시퀀스를 교환합니다. 일정 한 시간에 작업을 수행 하 고 예외가 throw 됩니다. 두 컨테이너의 내용을 교환에 신속 하 게 사용 합니다.  
  
### <a name="example"></a>예  
  
```cpp 
// cliext_list_swap.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::list<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```   

## <a name="to_array"></a> list:: to_array (STL/CLR)
제어 되는 새 배열에 복사합니다.  
  
### <a name="syntax"></a>구문  
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스를 포함 하는 배열을 반환 합니다. 배열 형식으로 제어 되는 시퀀스의 복사본을 사용 하면 됩니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  

## <a name="unique"></a> list:: unique (STL/CLR)
지정된 테스트를 통과하는 인접 요소를 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pred  
 요소 쌍에 대 한 비교자입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 제어 된 시퀀스 (지우기로 적용)에서 제거 하는 경우를 비교 하는 모든 요소가 이전 요소-같음 요소 `X` 요소 앞에 오는 `Y` 및 `X == Y`, 멤버 함수를 제거 `Y`합니다. 사용할 있습니다 인접 요소의 모든 하위 시퀀스의 복사본을 하나만 남기고 모두 제거 하려면 해당 비교 같음. 되는 경우 제어 되는 시퀀스 정렬 되는 경우 등으로 호출 하 여 [list:: sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`, 멤버 함수는 고유 값이 있는 요소를 둡니다. (그래서 이러한 이름을 갖습니다.)  
  
 두 번째 멤버 함수는 동일 하 게 동작 첫 번째, 각 요소를 제거 한다는 점을 제외 하면 `Y` 요소는 다음에 오는 `X` 입니다 `pred(X, Y)`합니다. 조건자 함수 또는 사용자가 지정한 대리자를 충족 하는 인접 요소의 모든 하위 시퀀스의 복사본을 하나만 남기고 모두 제거 하려면 사용 합니다. 되는 경우 제어 되는 시퀀스 정렬 되는 경우 등으로 호출 하 여 `sort(pred)`, 멤버 함수는 다른 요소와 순서 지정이 동일할 갖지 않는 요소만를 둡니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  

## <a name="value_type"></a> list:: value_type (STL/CLR)
요소의 형식입니다.  
  
### <a name="syntax"></a>구문  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Value`의 동의어입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_value_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::list<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
``` 

## <a name="op_neq"></a> operator! = (list) (STL/CLR)
같지 않음 비교를 나열 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator!=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 연산자 함수 반환 `!(left == right)`합니다. 테스트를 사용 하는지 여부를 `left` 동일 정렬 되지 않은 `right` 두 목록의 요소 별로 비교를 하는 경우.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_ne.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  

## <a name="op_lt"></a> 연산자&lt; (list) (STL/CLR)
목록 비교 보다 작습니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator<(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 연산자 함수 이면 true를 반환, 가장 낮은 위치에 대 한 `i` 를 `!(right[i] < left[i])` 도 true 하는 것이 `left[i] < right[i]`합니다. 그렇지 않으면 반환 `left->size() < right->size()` 테스트를 사용 하는지 여부를 `left` 앞에 정렬 `right` 두 목록의 요소 별로 비교를 하는 경우.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_lt.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  

## <a name="op_lteq"></a> 연산자&lt;= (list) (STL/CLR)
목록 보다 작거나 같은지 비교 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator<=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 연산자 함수 반환 `!(right < left)`합니다. 테스트를 사용 하는지 여부를 `left` 후 정렬 되지 않은 `right` 두 목록의 요소 별로 비교를 하는 경우.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_le.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  

## <a name="op_eq"></a> 연산자 = = (list) (STL/CLR)
같음 비교를 나열 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator==(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 연산자 함수는 시퀀스에 의해 제어 하는 경우에 true를 반환 `left` 및 `right` 동일한 길이 및 각 위치에 대 한 `i`, `left[i] ==` `right[i]`합니다. 테스트를 사용 하는지 여부를 `left` 와 동일 하 게 정렬 되 `right` 두 목록의 요소 별로 비교를 하는 경우.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_eq.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  

## <a name="op_gt"></a> 연산자&gt; (list) (STL/CLR)
목록 비교 보다 큽니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator>(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 연산자 함수 반환 `right` `<` `left`합니다. 테스트를 사용 하는지 여부를 `left` 후 정렬 `right` 두 목록의 요소 별로 비교를 하는 경우.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_gt.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  

## <a name="op_gteq"></a> 연산자&gt;= (list) (STL/CLR)
보다 큰 목록 또는 같은지 비교 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<typename Value>  
    bool operator>=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>매개 변수  
 왼쪽  
 비교할 왼쪽 컨테이너입니다.  
  
 오른쪽  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 연산자 함수 반환 `!(left` `<` `right)`합니다. 테스트를 사용 하는지 여부를 `left` 하기 전에 정렬 되지 않은 `right` 두 목록의 요소 별로 비교를 하는 경우.  
  
### <a name="example"></a>예  
  
```cpp  
// cliext_list_operator_ge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  
