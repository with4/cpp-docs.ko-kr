---
title: "this 포인터 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "this"
  - "this_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비정적 멤버 함수"
  - "포인터, 클래스 인스턴스"
  - "this 포인터"
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# this 포인터
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**this** 포인터는 **클래스**, `struct` 또는 **공용 구조체** 형식의 비정적 멤버 함수에서만 액세스할 수 있는 포인터이며  멤버 함수가 호출되는 개체를 가리킵니다.  비정적 멤버 함수는 **this** 포인터를 갖지 않습니다.  
  
## 구문  
  
```  
  
        this   
this->member-identifier  
```  
  
## 설명  
 개체의 **this** 포인터는 개체 자체의 일부분이 아니며 개체의 `sizeof` 문에 대한 결과에 반영되지 않습니다.  대신 비정적 멤버 함수가 개체에 대해 호출되는 경우 컴파일러가 개체의 주소를 숨겨진 인수로 함수에 전달합니다.  예를 들어, 다음 함수 호출은  
  
```  
myDate.setMonth( 3 );  
```  
  
 이렇게 해석할 수 있습니다.  
  
```  
setMonth( &myDate, 3 );  
```  
  
 개체의 주소를 멤버 함수 안에서 **this** 포인터로 사용할 수 있습니다.  대개 **this**는 암시적으로 사용됩니다.  클래스의 멤버를 참조할 때는 **this**를 명시적으로 사용하는 것이 좋습니다.  예:  
  
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
  
 **this** 포인터를 사용하여 자신에 대한 참조를 막기도 합니다.  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  **this** 포인터는 수정할 수 없으므로 **this**에 할당할 수 없습니다.  이전의 C\+\+ 구현에서는 **this**에 할당할 수 있었습니다.  
  
 예를 들어, 현재 개체의 주소가 필요할 경우 자신을 참조하는 데이터를 조작하기 위해 **this** 포인터를 직접 사용하기도 합니다.  
  
## 예제  
  
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
  
  **my buffer**  
**your buffer**   
## this 포인터 형식  
 **const** 및  **키워드를 사용하면 함수 선언에서 `volatile`this** 포인터의 형식을 수정할 수 있습니다.  이러한 키워드 하나 이상의 특성을 포함하도록 함수를 선언하려면 함수 인수 목록 뒤에 키워드를 추가합니다.  
  
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
  
 위의 코드는 `X` 멤버 함수를 선언합니다. 여기서 **this** 포인터는 **const** 개체에 대한 **const** 포인터로 처리됩니다.  *cv\-mod\-list* 옵션 조합도 사용할 수 있지만, 사용하는 경우 항상 **this** 포인터 자체가 아니라 **this**가 가리키는 개체가 수정됩니다.  따라서 다음 선언은 `X` 함수를 선언하며 **this** 포인터는 **const** 개체에 대한 **const** 포인터입니다.  
  
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
  
 멤버 함수에서 **this**의 형식은 다음 구문으로 설명됩니다. 여기서 *cv\-qualifier\-list*는 멤버 함수 선언자에서 결정되며 **const** 또는 **volatile**이거나 둘 다일 수 있고, *class\-type*은 클래스의 이름입니다.  
  
 *\[cv\-qualifier\-list\] class\-type*  **\* const this**  
  
 즉, **this**는 항상 const 포인터이며 다시 할당할 수 없습니다.  멤버 함수 선언에서 사용되는 **const** 또는 `volatile` 한정자는 해당 함수 범위의 **this**가 가리키는 클래스 인스턴스에 적용됩니다.  
  
 다음 표에서 이러한 한정자의 작동 방식에 대해 자세히 설명합니다.  
  
### 한정자의 의미  
  
|한정자|의미|  
|---------|--------|  
|**const**|멤버 데이터를 변경할 수 없습니다. **const**가 아닌 멤버 함수는 호출할 수 없습니다.|  
|`volatile`|액세스할 때마다 메모리에서 멤버 데이터를 로드하고 특정 최적화를 비활성화합니다.|  
  
 **const** 개체를 **const**가 아닌 멤버 함수로 전달할 때 발생하는 오류입니다.  마찬가지로 `volatile` 개체를 `volatile`이 아닌 멤버 함수로 전달할 때 발생하는 오류입니다.  
  
 **const**로 선언된 멤버 함수는 멤버 데이터를 변경할 수 없습니다. 이러한 함수에서 **this** 포인터는 **const** 개체에 대한 포인터입니다.  
  
> [!NOTE]
>  생성자와 소멸자는 **const** 또는 `volatile`로 선언할 수 없습니다.  그러나 **const** 또는 `volatile` 개체에 대해 생성자와 소멸자를 호출할 수는 있습니다.  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [this 포인터 형식](../misc/type-of-this-pointer.md)   
 [인수 일치 및 this 포인터](../misc/argument-matching-and-the-this-pointer.md)