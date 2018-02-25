---
title: "&lt;unordered_set&gt; 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unordered_set/std::swap (set)
- unordered_set/std::swap (unordered_multiset)
ms.assetid: 66b35671-4023-4411-ad50-83786580d8ee
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: f59431293fa738a332a09e2751b0087caabd460e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltunorderedsetgt-functions"></a>&lt;unordered_set&gt; 함수
|||  
|-|-|  
|[swap (set)](#swap)|[swap (unordered_multiset)](#swap_unordered_multiset)|  
  
##  <a name="swap"></a>  swap (unordered_set)  
 두 컨테이너의 내용을 바꿉니다.  
  
```  
 
template <class Key, class Hash, class Pred, class Alloc>  
void swap(
   unordered_set <Key, Hash, Pred, Alloc>& left,  
   unordered_set <Key, Hash, Pred, Alloc>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Key`  
 키 형식입니다.  
  
 `Hash`  
 해시 함수 개체 형식입니다.  
  
 `Pred`  
 같음 비교 함수 개체 형식입니다.  
  
 `Alloc`  
 할당자 클래스입니다.  
  
 `left`  
 교환할 첫 번째 컨테이너입니다.  
  
 `right`  
 교환할 두 번째 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수는 `left.`[unordered_set::swap](../standard-library/unordered-set-class.md#swap)`(right)`을 실행합니다.  
  
### <a name="example"></a>예  
  
```cpp  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
Myset c2;  
  
c2.insert('d');  
c2.insert('e');  
c2.insert('f');  
  
c1.swap(c2);  
  
// display contents " [f] [e] [d]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
swap(c1, c2);  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[f] [e] [d]  
[c] [b] [a]  
  
```  
  
##  <a name="swap_unordered_multiset"></a>  swap (unordered_multiset) 
 두 컨테이너의 내용을 바꿉니다.  
  
```  
 
template <class Key, class Hash, class Pred, class Alloc>  
void swap(
   unordered_multiset <Key, Hash, Pred, Alloc>& left,  
   unordered_multiset <Key, Hash, Pred, Alloc>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Key`  
 키 형식입니다.  
  
 `Hash`  
 해시 함수 개체 형식입니다.  
  
 `Pred`  
 같음 비교 함수 개체 형식입니다.  
  
 `Alloc`  
 할당자 클래스입니다.  
  
 `left`  
 교환할 첫 번째 컨테이너입니다.  
  
 `right`  
 교환할 두 번째 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수는 `left.`[unordered_multiset::swap](../standard-library/unordered-multiset-class.md#swap)`(right)`을 실행합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// std__unordered_set__u_ms_swap.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents " [f] [e] [d]"  
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    return (0);
}
  
```  
  
```Output  
  
[c] [b] [a]  
[f] [e] [d]  
[c] [b] [a]  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [<unordered_set>](../standard-library/unordered-set.md)

