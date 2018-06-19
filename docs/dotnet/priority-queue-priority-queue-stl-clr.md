---
title: 'priority_queue:: priority_queue (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue member [STL/CLR]
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8cb50eed9dbfcbe9480a6588ff10f966f1888205
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163395"
---
# <a name="priorityqueuepriorityqueue-stlclr"></a>priority_queue::priority_queue(STL/CLR)
컨테이너 어댑터 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### <a name="parameters"></a>매개 변수  
 계속  
 복사할 컨테이너입니다.  
  
 첫 번째  
 삽입할 범위의의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 pred  
 제어 되는 시퀀스에 대 한 조건자를 정렬 합니다.  
  
 오른쪽  
 삽입할 개체 또는 범위입니다.  
  
## <a name="remarks"></a>설명  
 생성자:  
  
 `priority_queue();`  
  
 기본 조건자를 정렬 된 빈 래핑된 컨테이너를 만듭니다. 기본 조건자를 정렬 된는 빈 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 복사본 인 래핑된 컨테이너를 만들고 `right.get_container()`, 정렬 조건부와 함께 `right.value_comp()`합니다. 큐 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `right`, 동일한 정렬 조건부와 함께 합니다.  
  
 생성자:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 복사본 인 래핑된 컨테이너를 만들고 `right->get_container()`, 정렬 조건부와 함께 `right->value_comp()`합니다. 큐 개체에 의해 제어 되는 시퀀스의 복사본 인는 초기 제어 시퀀스를 지정 하려면 사용할 `*right`, 동일한 정렬 조건부와 함께 합니다.  
  
 생성자:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 정렬 조건자가 있는 빈 래핑된 컨테이너를 만들고 `pred`합니다. 지정 된 정렬 조건부와 함께 빈 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 정렬 조건자가 있는 빈 래핑된 컨테이너를 만들고 `pred`, 다음의 모든 요소를 푸시합니다 `cont` 사용 하면 지정 된 정렬 조건부와 함께 기존 컨테이너에서 제어 되는 초기 시퀀스를 지정할 수 있습니다.  
  
 생성자:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 기본 정렬 조건부와 함께 빈 래핑된 컨테이너를 만든 다음이 푸시 시퀀스 [`first`, `last`). 지정 된 정렬 조건부와 함께 지정된 eqeuence에서 제어 되는 초기 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 정렬 조건자가 있는 빈 래핑된 컨테이너를 만들고 `pred`, 시퀀스 푸시합니다 [`first`, `last`). 지정 된 정렬 조건부와 함께 지정된 seqeuence에서 제어 되는 초기 시퀀스를 지정 하려면 사용 합니다.  
  
 생성자:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 정렬 조건자가 있는 빈 래핑된 컨테이너를 만들고 `pred`, 다음의 모든 요소를 푸시합니다 `cont` 시퀀스 더하기 [`first`, `last`). 지정 된 정렬 조건부와 함께 기존 컨테이너를 지정 된 seqeuence는 초기 제어 시퀀스를 지정 하려면 사용 합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue:: assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority_queue:: generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority_queue::operator=(STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)