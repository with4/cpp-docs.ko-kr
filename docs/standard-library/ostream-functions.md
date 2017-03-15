---
title: "&lt;ostream&gt; 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 44708461657101b1ddad7db76f1c3c8d4df07f3a
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 함수
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="a-nameendla--endl"></a><a name="endl"></a>  endl  
 줄을 종료하고 버퍼를 플러시합니다.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& endl(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>매개 변수  
 `Elem`  
 요소 형식입니다.  
  
 `Ostr`  
 `basic_ostream` 형식의 개체입니다.  
  
 `Tr`  
 문자 특성입니다.  
  
### <a name="return-value"></a>반환 값  
 `basic_ostream` 형식의 개체입니다.  
  
### <a name="remarks"></a>설명  
 조작자는 `Ostr`**.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Ostr`**.** [widen](../standard-library/basic-ios-class.md#basic_ios__widen)( **'\n'**))을 호출한 다음 `Ostr`**.** [flush](../standard-library/basic-ostream-class.md#basic_ostream__flush)를 호출하고 `Ostr`를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// ostream_endl.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << endl;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="a-nameendsa--ends"></a><a name="ends"></a>  ends  
 문자열을 종료합니다.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& ends(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>매개 변수  
 `Elem`  
 요소 형식입니다.  
  
 `Ostr`  
 `basic_ostream` 형식의 개체입니다.  
  
 `Tr`  
 문자 특성입니다.  
  
### <a name="return-value"></a>반환 값  
 `basic_ostream` 형식의 개체입니다.  
  
### <a name="remarks"></a>설명  
 조작자는 `Ostr`**.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Elem`( **'\0'**))을 호출하고 `Ostr.`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// ostream_ends.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "a";  
   cout << "b" << ends;  
   cout << "c" << endl;  
}  
```  
  
```Output  
ab c  
```  
  
##  <a name="a-nameflusha--flush"></a><a name="flush"></a>  flush  
 버퍼를 플러시합니다.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& flush(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>매개 변수  
 `Elem`  
 요소 형식입니다.  
  
 `Ostr`  
 `basic_ostream` 형식의 개체입니다.  
  
 `Tr`  
 문자 특성입니다.  
  
### <a name="return-value"></a>반환 값  
 `basic_ostream` 형식의 개체입니다.  
  
### <a name="remarks"></a>설명  
 조작자는 `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#basic_ostream__flush)를 호출하고 `Ostr`를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << flush;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 두 `basic_ostream` 개체의 값을 교환합니다.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 `basic_ostream` 개체에 대한 lvalue 참조입니다.  
  
 ` right`  
 `basic_ostream` 개체에 대한 lvalue 참조입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수 `swap`은 ` left.swap(`` right``)`을 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<ostream>](../standard-library/ostream.md)


