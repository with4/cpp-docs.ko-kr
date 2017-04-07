---
title: "&lt;hash_map&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6960d7dfc3a6f36f803ae765ad4cbeb77038401c
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator!=(hash_map)](#operator_neq__hash_map_)|[operator==](#operator_eq_eq)|  
|[operator==(hash_map)](#operator_eq_eq__hash_map_)|  
  
##  <a name="operator_neq__hash_map_"></a>  operator!=(hash_map)  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_map 클래스](../standard-library/unordered-map-class.md)를 대신 사용하는 것이 좋습니다.  
  
 연산자의 좌변에 있는 hash_map 개체가 우변에 있는 hash_map 개체와 같지 않은지 테스트합니다.  
  
```  
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `hash_map` 형식의 개체입니다.  
  
 `right`  
 `hash_map` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 hash_map이 같지 않으면 **true**이고, hash_map이 같으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 hash_map 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 hash_map은 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// hash_map_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="operator_eq_eq__hash_map_"></a>  operator==(hash_map)  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_map 클래스](../standard-library/unordered-map-class.md)를 대신 사용하는 것이 좋습니다.  
  
 연산자의 좌변에 있는 hash_map 개체가 우변에 있는 hash_map 개체와 같은지 테스트합니다.  
  
```  
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `hash_map` 형식의 개체입니다.  
  
 `right`  
 `hash_map` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 hash_map이 연산자 우변의 hash_map과 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 hash_map 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 hash_map은 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// hash_map_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="operator_neq"></a>  operator!=  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_multimap 클래스](../standard-library/unordered-multimap-class.md)를 대신 사용하는 것이 좋습니다.  
  
 연산자의 좌변에 있는 hash_multimap 개체가 우변에 있는 hash_multimap 개체와 같지 않은지 테스트합니다.  
  
```  
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `hash_multimap` 형식의 개체입니다.  
  
 `right`  
 `hash_multimap` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 hash_multimap이 같지 않으면 **true**이고, hash_multimap이 같으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 hash_multimap 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 hash_multimap은 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// hash_multimap_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
##  <a name="operator_eq_eq"></a>  operator==  
  
> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다. [unordered_multimap 클래스](../standard-library/unordered-multimap-class.md)를 대신 사용하는 것이 좋습니다.  
  
 연산자의 좌변에 있는 hash_multimap 개체가 우변에 있는 hash_multimap 개체와 같은지 테스트합니다.  
  
```  
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `left`  
 `hash_multimap` 형식의 개체입니다.  
  
 `right`  
 `hash_multimap` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 연산자 좌변의 hash_multimap이 연산자 우변의 hash_multimap과 같으면 **true**이고 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 hash_multimap 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 hash_multimap은 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.  
  
 Visual C++ .NET 2003에서 [<hash_map>](../standard-library/hash-map.md) 및 [<hash_set>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 있지 않으며 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### <a name="example"></a>예제  
  
```cpp  
// hash_multimap_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair<int, int> Int_Pair;  
  
   for (i = 0; i < 3; i++)  
   {  
      hm1.insert(Int_Pair(i, i));  
      hm2.insert(Int_Pair(i, i*i));  
      hm3.insert(Int_Pair(i, i));  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
## <a name="see-also"></a>참고 항목  
 [<hash_map>](../standard-library/hash-map.md)


