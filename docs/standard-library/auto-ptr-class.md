---
title: "auto_ptr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- auto_ptr
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
dev_langs:
- C++
helpviewer_keywords:
- auto_ptr class
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 320dbc4d09bfcc65fce8471ce23e127f28deb6b9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="autoptr-class"></a>auto_ptr 클래스
제어가 블록을 나갈 때 리소스가 자동으로 제거되도록 리소스를 스마트 포인터로 래핑합니다.  
  
 더욱 강력한 `unique_ptr` 클래스가 `auto_ptr`을 대체합니다. 자세한 내용은 [unique_ptr 클래스](../standard-library/unique-ptr-class.md)를 참조하세요.  
  
 `throw()` 및 예외 처리에 대한 자세한 내용은 [예외 사양(throw)](../cpp/exception-specifications-throw-cpp.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
 ```   
class auto_ptr {
public:
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```  
#### <a name="parameters"></a>매개 변수  
 `right`  
 기존 리소스를 가져올 `auto_ptr`입니다.  
  
 `ptr`  
 저장된 포인터를 바꾸도록 지정된 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이라는 스마트 포인터를 설명 하는 템플릿 클래스는 `auto_ptr`, 할당 된 개체입니다. 포인터는 null이거나 `new`로 할당된 개체를 지정해야 합니다. 저장된 값이 다른 개체에 할당되면 `auto_ptr`이 소유권을 전송합니다. null 포인터를 사용한 전송 후 저장된 값을 대체합니다. `auto_ptr<Type>`에 대한 소멸자는 할당된 개체를 삭제합니다. `auto_ptr<Type>`은 예외가 발생하는 경우에도 제어가 블록을 나갈 때 할당된 개체가 자동으로 삭제되도록 합니다. 동일한 개체를 소유하는 두 개의 `auto_ptr<Type>` 개체를 생성하면 안 됩니다.  
  
 함수 호출에 대한 인수로 `auto_ptr<Type>` 개체 값을 전달할 수 있습니다. `auto_ptr`은 표준 라이브러리 컨테이너의 요소일 수 없습니다. C++ 표준 라이브러리 컨테이너를 사용하여 `auto_ptr<Type>` 개체의 시퀀스를 안정적으로 관리할 수 없습니다.  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[auto_ptr](#auto_ptr)|`auto_ptr` 형식의 개체에 대한 생성자입니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[element_type](#element_type)|이 형식은 템플릿 매개 변수 `Type`의 동의어입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[get](#get)|이 멤버 함수는 저장된 포인터 `myptr`을 반환합니다.|  
|[release](#release)|이 멤버는 저장된 포인터 `myptr`을 null 포인터로 대체하고 이전에 저장된 포인터를 반환합니다.|  
|[reset](#reset)|이 멤버 함수는 저장된 포인터 값 `myptr`이 함수 호출의 결과로 변경되는 경우에만 `delete myptr` 식을 계산합니다. 그런 다음 저장된 포인터를 `ptr`로 바꿉니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator=](#op_eq)|한 `auto_ptr` 개체에서 다른 개체로 소유권을 전송하는 대입 연산자입니다.|  
|[operator*](#op_star)|`auto_ptr` 형식의 개체에 대한 역참조 연산자입니다.|  
|[operator->](#operator-_gt)|멤버 액세스를 허용하기 위한 연산자입니다.|  
|[operator auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|한 종류의 `auto_ptr`에서 다른 종류의 `auto_ptr`로 캐스팅합니다.|  
|[operator auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|`auto_ptr`에서 `auto_ptr_ref`로 캐스팅합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<memory>  
  
 **네임스페이스:** std  
  
##  <a name="auto_ptr"></a>  auto_ptr::auto_ptr  
 `auto_ptr` 형식의 개체에 대한 생성자입니다.  
  
```   
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>  
auto _ptr(auto _ptr<Other>& right) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ptr`  
 `auto_ptr`이 캡슐화하는 개체에 대한 포인터입니다.  
  
 `right`  
 생성자에 의해 복사될 `auto_ptr` 개체입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 할당된 개체에 대한 저장된 포인터인 **myptr**에 `ptr`을 저장합니다. 두 번째 생성자에 저장 된 포인터의 소유권을 전송 `right`를 저장 하 여 `right`합니다. [release](#release)를 **myptr**에 저장합니다.  
  
 세 번째 생성자도 두 번째와 동일하게 동작합니다. 단, **right**. `ref`. **release**를 **myptr**에 저장한다는 점이 다릅니다. 여기서 `ref`는 `right`에 저장된 참조입니다.  
  
 **Other**에 대한 포인터가 **Type**에 대한 포인터로 암시적으로 변환될 수 있는 경우, 템플릿 생성자는 두 번째 생성자와 동일하게 동작합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// auto_ptr_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
void function ( auto_ptr<Int> &pi )  
{  
   ++( *pi );  
   auto_ptr<Int> pi2( pi );  
   ++( *pi2 );  
   pi = pi2;  
}  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   cout << pi->x << endl;  
   function( pi );  
   cout << pi->x << endl;  
}  
```  
  
```Output  
Constructing 00311AF8  
5  
7  
Destructing 00311AF8  
```  
  
##  <a name="element_type"></a>  auto_ptr::element_type  
 이 형식은 템플릿 매개 변수 **Type**의 동의어입니다.  
  
```  
 
typedef Type element  _type;  
```  
  
##  <a name="get"></a>  auto_ptr::get  
 이 멤버 함수는 저장된 포인터 **myptr**을 반환합니다.  
  
```   
Type *get() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 저장된 포인터 **myptr**입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// auto_ptr_get.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      x = i;  
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;   
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;   
   };  
  
   int x;  
  
};  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   pi.reset( new Int( 6 ) );  
   Int* pi2 = pi.get ( );  
   Int* pi3 = pi.release ( );  
   if (pi2 == pi3)  
      cout << "pi2 == pi3" << endl;  
   delete pi3;  
}  
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="op_eq"></a>  auto_ptr::operator=  
 한 `auto_ptr` 개체에서 다른 개체로 소유권을 전송하는 대입 연산자입니다.  
  
```  
template <class Other>  
auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 `auto_ptr` 형식의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `auto_ptr`\< **Type**> 형식의 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 할당은 저장된 포인터 **myptr**이 할당의 결과로 변경되는 경우에만 **delete myptr** 식을 계산합니다. 그런 다음 _ *Right*에 저장된 포인터의 소유권을 전송하기 위해 \_ *Right*. [release](#release)를 **myptr**에 저장합니다. 함수는 **\*this**를 반환합니다.  
  
### <a name="example"></a>예제  
  멤버 연산자의 사용 예는 [auto_ptr::auto_ptr](#auto_ptr)을 참조하세요.  
  
##  <a name="op_star"></a>  auto_ptr::operator*  
 `auto_ptr` 형식의 개체에 대한 역참조 연산자입니다.  
  
```   
Type& operator*() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 포인터가 소유한 **Type** 형식의 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 간접 참조 연산자는 `*`[get](#get)을 반환합니다. 따라서 저장된 포인터는 null이 아니어야 합니다.  
  
### <a name="example"></a>예제  
  멤버 함수를 사용하는 방법의 예는 [auto_ptr::auto_ptr](#auto_ptr)을 참조하세요.  
  
##  <a name="auto_ptr__operator-_gt"></a>  auto_ptr::operator-&gt;  
 멤버 액세스를 허용하기 위한 연산자입니다.  
  
```   
Type * operator->() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 **auto_ptr**을 소유한 개체의 멤버입니다.  
  
### <a name="remarks"></a>설명  
 선택 연산자는 [get](#get)`( )`을 반환합니다. 따라서 *ap*-> **member** 식은 ( *ap*. **get**( ) )-> **member**와 동일하게 동작합니다. 여기서 *ap*는 `auto_ptr`\< **Type**> 클래스의 개체입니다. 따라서 저장된 포인터는 null이 아니어야 하며, **Type**은 클래스, 구조체 또는 **member** 멤버가 있는 공용 구조체 형식이어야 합니다.  
  
### <a name="example"></a>예제  
  멤버 함수를 사용하는 방법의 예는 [auto_ptr::auto_ptr](#auto_ptr)을 참조하세요.  
  
##  <a name="op_auto_ptr_lt_other_gt"></a>  auto_ptr::operator auto_ptr&lt;Other&gt;  
 한 종류의 `auto_ptr`에서 다른 종류의 `auto_ptr`로 캐스팅합니다.  
  
```   
template <class Other>  
operator auto _ptr<Other>() throw();
```  
  
### <a name="return-value"></a>반환 값  
 형식 캐스팅 연산자는 `auto_ptr` \< **Other**>( **\*this**)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// auto_ptr_op_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
int main()  
{  
   auto_ptr<int> pi ( new int( 5 ) );  
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;  
}  
```  
  
##  <a name="op_auto_ptr_ref_lt_other_gt"></a>  auto_ptr::operator auto_ptr_ref&lt;Other&gt;  
 `auto_ptr`에서 **auto_ptr_ref**로 캐스트합니다.  
  
```   
template <class Other>  
operator auto _ptr  _ref<Other>() throw();
```  
  
### <a name="return-value"></a>반환 값  
 형식 캐스팅 연산자는 **auto_ptr_ref**\< **Other**>( **\*this**)를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// auto_ptr_op_auto_ptr_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer  
    // f(ciap);   
    f(iap); // compiles, but gives up ownership of pointer  

            // here, iap owns a destroyed pointer so the following is bad:  
            // *iap = 5; // BOOM  

    cout << "main exiting\n";
}
```  
  
```Output  
~C:  2  
main exiting  
~C:  1  
```  
  
##  <a name="release"></a>  auto_ptr::release  
 이 멤버는 저장된 포인터 **myptr**을 null 포인터로 대체하고 이전에 저장된 포인터를 반환합니다.  
  
```   
Type *release() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 저장된 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버는 저장된 포인터 **myptr**을 null 포인터로 대체하고 이전에 저장된 포인터를 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// auto_ptr_release.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="reset"></a>  auto_ptr::reset  
 멤버 함수는 식을 계산 **삭제** **myptr**, 경우에 저장 된 포인터 값 **myptr** 함수 호출의 결과로 변경 합니다. 그런 다음 저장된 포인터를 **ptr**로 바꿉니다.  
  
```   
void reset(Type* ptr = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptr`  
 저장된 포인터 **myptr**을 바꾸도록 지정된 포인터입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// auto_ptr_reset.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique_ptr 클래스](../standard-library/unique-ptr-class.md)


