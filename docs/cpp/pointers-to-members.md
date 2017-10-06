---
title: "멤버의 포인터에 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 98a6db086443c15964a1dcf0a345b2fbaccfa233
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="pointers-to-members"></a>pointers_to_members
멤버에 대한 포인터 선언은 포인터 선언의 특별한 경우입니다.  이러한 함수는 다음 시퀀스를 사용하여 선언됩니다.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier  
[= & qualified-name :: member-name];  
```  
  
1.  선언 지정자:  
  
    -   선택적 저장소 클래스 지정자.  
  
    -   선택적 **const** 및/또는 `volatile` 지정자입니다.  
  
    -   형식 지정자: 형식의 이름  이는 클래스가 아니라 가리킬 멤버의 형식입니다.  
  
2.  선언자:  
  
    -   선택적 Microsoft 전용 한정자. 자세한 내용은 참조 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)합니다.  
  
    -   가리킬 멤버가 포함된 클래스의 정규화된 이름입니다.   
  
    -   :: 연산자  
  
    -   ** \* ** 연산자입니다.  
  
    -   선택적 **const** 및/또는 `volatile` 지정자입니다.  
  
    -   멤버에 대한 포인터의 이름을 지정하는 식별자  
  
    -   선택적 이니셜라이저:  
  
 ** = ** 연산자입니다.  
  
 ** & ** 연산자입니다.  
  
 클래스의 정규화된 이름  
  
 `::` 연산자  
  
 적절한 형식의 클래스의 비정적 멤버 이름  
  
 항상 그렇듯이 여러 선언자(및 모든 관련 이니셜라이저)가 단일 선언에서 허용됩니다.  
  
 클래스의 멤버에 대한 포인터는 멤버의 형식과 멤버가 속한 클래스에 대한 형식 정보를 포함하기 때문에 일반 포인터와 다릅니다. 일반 포인터는 메모리에 있는 단일 개체만 식별합니다(해당 개체의 주소를 포함함). 클래스의 멤버에 대한 포인터는 클래스의 모든 인스턴스에서 해당 멤버를 식별합니다. 다음 예제에서는 `Window` 클래스와 멤버 데이터에 대한 몇 가지 포인터를 선언합니다.  
  
```  
// pointers_to_members1.cpp  
class Window  
{  
public:  
   Window();                               // Default constructor.  
   Window( int x1, int y1,                 // Constructor specifying  
   int x2, int y2 );                       //  window size.  
bool SetCaption( const char *szTitle ); // Set window caption.  
   const char *GetCaption();               // Get window caption.  
   char *szWinCaption;                     // Window caption.  
};  
  
// Declare a pointer to the data member szWinCaption.  
char * Window::* pwCaption = &Window::szWinCaption;  
int main()  
{  
}  
```  
  
 앞의 예제에서 `pwCaption` 클래스의 모든 멤버에 대 한 포인터 `Window` 형식을 가진를 **char\***합니다. `pwCaption`의 형식은 `char * Window::*`입니다. 다음 코드에서는 `SetCaption` 및 `GetCaption` 멤버 함수에 대한 포인터를 선언합니다.  
  
```  
const char * (Window::*pfnwGC)() = &Window::GetCaption;  
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;  
```  
  
 `pfnwGC` 및 `pfnwSC` 포인터는 `GetCaption` 클래스의 `SetCaption` 및 `Window`을 각각 가리킵니다. 이 코드에서는 멤버에 대한 포인터 `pwCaption`을 직접 사용하여 창 캡션에 정보를 복사합니다.  
  
```  
Window wMainWindow;  
Window *pwChildWindow = new Window;  
char   *szUntitled    = "Untitled -  ";  
int    cUntitledLen   = strlen( szUntitled );  
  
strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );  
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     //same as  
//wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';  
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );   
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; //same as //pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';  
```  
  
 차이 **.\* ** 및 ** -> \* ** 연산자 (멤버 포인터 연산자)의 **.\* ** 연산자 멤버를 선택 하는 동안 개체 또는 개체 참조에 따라는 ** -> \* ** 연산자는 포인터를 통해 멤버를 선택 합니다. (이러한 연산자에 대 한 자세한 내용은 [멤버 포인터 연산자가 있는 식](../cpp/pointer-to-member-operators-dot-star-and-star.md).)  
  
 멤버 포인터 연산자의 결과 멤버의 유형을-이 경우 **char \* **합니다.  
  
 다음 코드에서는 멤버에 대한 포인터를 사용하여 `GetCaption` 및 `SetCaption` 멤버 함수를 호출합니다.  
  
```  
// Allocate a buffer.  
enum {  
    sizeOfBuffer = 100  
};  
char szCaptionBase[sizeOfBuffer];  
  
// Copy the main window caption into the buffer  
//  and append " [View 1]".  
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );  
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );  
// Set the child window's caption.  
(pwChildWindow->*pfnwSC)( szCaptionBase );  
```  
  
## <a name="restrictions-on-pointers-to-members"></a>멤버에 대한 포인터 제한  
 정적 멤버의 주소는 멤버에 대한 포인터가 아닙니다. 정적 멤버의 주소는 정적 멤버의 인스턴스 하나에 대한 일반적인 포인터입니다. 일반 주소 지정된 된 클래스의 모든 개체에 대 한 정적 멤버의 인스턴스 하나만 존재 하기 때문에 **(&)** 및 역참조 **(\*)** 연산자를 사용할 수 있습니다.  
  
## <a name="pointers-to-members-and-virtual-functions"></a>멤버 및 가상 함수에 대한 포인터  
 멤버 포인터 함수를 통해 가상 함수를 호출하는 것은 함수가 직접 호출된 것과 같으며, v-table에서 올바른 함수가 조회된 다음 호출됩니다.  
  
 가상 함수 작업은 항상 기본 클래스 포인터를 통해 호출합니다. (가상 함수에 대 한 자세한 내용은 참조 [가상 함수](../cpp/virtual-functions.md).)  
  
 다음 코드에서는 멤버 포인터 함수를 통해 가상 함수를 호출하는 방법을 보여 줍니다.  
  
```  
// virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:  
virtual void Print();  
};  
void (Base ::* bfnPrint)() = &Base :: Print;  
void Base :: Print()  
{  
cout << "Print function for class Base\n";  
}  
  
class Derived : public Base  
{  
public:  
void Print();  // Print is still a virtual function.  
};  
  
void Derived :: Print()  
{  
cout << "Print function for class Derived\n";  
}  
  
int main()  
{  
    Base   *bPtr;  
    Base    bObject;  
Derived dObject;  
bPtr = &bObject;    // Set pointer to address of bObject.  
(bPtr->*bfnPrint)();  
bPtr = &dObject;    // Set pointer to address of dObject.  
(bPtr->*bfnPrint)();  
}  
  
//Output: Print function for class Base  
Print function for class Derived  
```  
  
## <a name="see-also"></a>참고 항목  
 
