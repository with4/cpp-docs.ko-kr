---
title: "이 포인터 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: this_cpp
dev_langs: C++
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4e77139cdf93d385b92eb87483c1b03541b18650
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="this-pointer"></a>this 포인터
**이** 포인터는 포인터의 비정적 멤버 함수 내 에서만 액세스할 수는 **클래스**, `struct`, 또는 **union** 유형입니다. 멤버 함수가 호출되는 개체를 가리킵니다. 정적 멤버 함수를 포함 하지 않습니다는 **이** 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      this   
this->member-identifier  
```  
  
## <a name="remarks"></a>설명  
 개체의 **이** 포인터는 개체 자체의 일부가 아닙니다.의 결과에 반영 되지 않습니다는 `sizeof` 개체에서 문입니다. 대신 비정적 멤버 함수가 개체에 대해 호출되는 경우 컴파일러가 개체의 주소를 숨겨진 인수로 함수에 전달합니다. 예를 들어, 다음 함수 호출은  
  
```  
myDate.setMonth( 3 );  
```  
  
 이렇게 해석할 수 있습니다.  
  
```  
setMonth( &myDate, 3 );  
```  
  
 개체의 주소는 멤버 함수 내에서 사용할 수는 **이** 포인터입니다. 대부분 용도 **이** 는 암시적 합니다. 사용 하 여 명시적으로 법률, **이** 클래스의 멤버를 참조할 때. 예:  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 멤버 함수에서 현재 개체를 반환하기 위해 `*this` 식이 주로 사용됩니다.  
  
```  
return *this;  
```  
  
 **이** 포인터는 자기 참조 방지에 사용 됩니다.  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  때문에 **이** 포인터는 수정할 수에 대 한 할당 **이** 허용 되지 않습니다. C + +의 이전 구현에서는에 할당할 수 있었습니다. **이**합니다.  
  
 경우에 따라서는 **이** 포인터를 직접 사용-예를 들어 자체 참조 데이터를 조작 하기 위한 구조를 현재 개체의 주소가 필요 합니다.  
  
## <a name="example"></a>예제  
  
```  
// this_pointer.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
class Buf   
{  
public:  
    Buf( char* szBuffer, size_t sizeOfBuffer );  
    Buf& operator=( const Buf & );  
    void Display() { cout << buffer << endl; }  
  
private:  
    char*   buffer;  
    size_t  sizeOfBuffer;  
};  
  
Buf::Buf( char* szBuffer, size_t sizeOfBuffer )  
{  
    sizeOfBuffer++; // account for a NULL terminator  
  
    buffer = new char[ sizeOfBuffer ];  
    if (buffer)  
    {  
        strcpy_s( buffer, sizeOfBuffer, szBuffer );  
        sizeOfBuffer = sizeOfBuffer;  
    }  
}  
  
Buf& Buf::operator=( const Buf &otherbuf )   
{  
    if( &otherbuf != this )   
    {  
        if (buffer)  
            delete [] buffer;  
  
        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;   
        buffer = new char[sizeOfBuffer];  
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );  
    }  
    return *this;  
}  
  
int main()  
{  
    Buf myBuf( "my buffer", 10 );  
    Buf yourBuf( "your buffer", 12 );  
  
    // Display 'my buffer'  
    myBuf.Display();  
  
    // assignment opperator  
    myBuf = yourBuf;  
  
    // Display 'your buffer'  
    myBuf.Display();  
}  
```  
  
```Output  
my buffer  
your buffer  
```  
  
## <a name="type-of-the-this-pointer"></a>this 포인터 형식  
 **이** 의해 함수 선언에 포인터의 형식을 수정할 수는 **const** 및 `volatile` 키워드입니다. 이러한 키워드 하나 이상의 특성을 포함하도록 함수를 선언하려면 함수 인수 목록 뒤에 키워드를 추가합니다.  
  
 다음 예제를 고려해 보세요.  
  
```  
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 위의 코드는 멤버 함수를 선언 `X`는 **이** 포인터로 처리 되는 **const** 에 대 한 포인터는 **const** 개체입니다. 조합의 *cv mod 목록* 옵션을 사용할 수 있지만 항상가 가리키는 개체가 수정 **이**이 아니라는 **이** 포인터 자체입니다. 다음 선언에서 함수를 선언 하는 따라서 `X`; **이** 포인터가 **const** 에 대 한 포인터는 **const** 개체:  
  
```  
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 유형의 **이** 멤버 함수는 다음 구문을 사용 하 여 설명 되어 있는 *cv 한정자-목록* 수 및 멤버 함수 선언 자에서 결정 됩니다 **const**또는 **휘발성** (또는 둘 다) 및 *클래스 형식* 클래스의 이름입니다.  
  
 *클래스 유형 [cv 한정자 목록]*  **\* const이**   
  
 즉, **이** 는 항상 const 포인터 이며 다시 할당할 수 없습니다.  **const** 또는 `volatile` 멤버 함수 선언에서 사용 되는 한정자가 가리키는 클래스 인스턴스에 적용 **이** 해당 함수의 범위에 있습니다.  
  
 다음 표에서 이러한 한정자의 작동 방식에 대해 자세히 설명합니다.  
  
### <a name="semantics-of-this-modifiers"></a>한정자의 의미  
  
|한정자|의미|  
|--------------|-------------|  
|**const**|멤버 데이터를 변경할 수 없습니다. 멤버 함수를 호출할 수 없습니다. **const**합니다.|  
|`volatile`|액세스할 때마다 메모리에서 멤버 데이터를 로드하고 특정 최적화를 비활성화합니다.|  
  
 전달 하면 오류가 발생 한 **const** 하지 않은 멤버 함수에 개체 **const**합니다. 마찬가지로 `volatile` 개체를 `volatile`이 아닌 멤버 함수로 전달할 때 발생하는 오류입니다.  
  
 로 선언 된 멤버 함수 **const** 멤버 데이터를 변경할 수 없습니다-이러한 함수는 **이** 포인터에 대 한 포인터는 한 **const** 개체입니다.  
  
> [!NOTE]
>  생성자 및 소멸자로 선언할 수 없습니다 **const** 또는 `volatile`합니다. 그러나 수 수에 대해 호출할 **const** 또는 `volatile` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 