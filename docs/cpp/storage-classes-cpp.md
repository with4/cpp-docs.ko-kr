---
title: "저장소 클래스 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
dev_langs:
- C++
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
caps.latest.revision: 13
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
ms.openlocfilehash: db5a6c23d11f8cdf144e42aee4880ee1ac26066a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="storage-classes-c"></a>저장소 클래스(C++)  
  
A *저장소 클래스* c + +의 컨텍스트에서 변수 선언은 개체의 수명, 링크 및 메모리 위치를 제어 하는 형식 지정자입니다. 주어진 개체에는 저장소 클래스가 하나만 있을 수 있습니다. `extern`, `static`또는 `thread_local` 지정자를 사용하여 달리 지정되지 않은 경우 블록 내에 정의된 변수는 자동 저장소를 갖습니다. 자동 개체 및 변수는 링크가 없으며 블록 외부의 코드에 표시되지 않습니다.  
  
**참고**  
  
1.  [변경 가능한](../cpp/mutable-data-members-cpp.md) 키워드는 저장소 클래스 지정자를 고려 될 수 있습니다. 하지만 클래스 정의의 멤버 목록에만 사용할 수 있습니다.  
  
2.  **Visual c + + 2010 이상:** 는 `auto` 키워드는 c + + 저장소 클래스 지정자를 사용 하는 더 이상 및 `register` 키워드는 사용 되지 않습니다. **Visual Studio 2017 15.3 이상 버전:** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):는 `register` 키워드는 더 이상 지원 되는 저장소 클래스입니다. 키워드는 나중에 사용할 표준에서 계속 예약 되어 있습니다. 
```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>섹션 내용
  
-   [static](#static)  
-   [extern](#extern)  
-   [thread_local](#thread_local)

<a name="static"></a>
  
## <a name="static"></a>정적  
  
`static` 키워드는 전역 범위, 네임스페이스 범위 및 클래스 범위에서 변수와 함수를 선언하는 데 사용할 수 있습니다. 정적 변수는 로컬 범위에서 선언할 수도 있습니다.  
  
정적 생존 기간이란 프로그램이 시작될 때 개체 또는 변수가 할당되고 프로그램이 끝날 때 개체 또는 변수가 할당 취소됨을 의미합니다. 외부 연결은 변수가 선언된 파일 외부에서 변수 이름이 표시됨을 의미합니다. 반대로 내부 연결은 변수가 선언된 파일 외부에 이름이 표시되지 않음을 의미합니다. 기본적으로 전역 네임스페이스에서 정의된 개체 또는 변수에는 정적 지속 기간 및 외부 링크가 있습니다. `static` 키워드는 다음 상황에서 사용할 수 있습니다.  
  
1.  파일 범위(전역 및/또는 네임스페이스 범위)에 변수 또는 함수를 선언한 경우, `static` 키워드는 변수 또는 함수에 내부 링크가 있음을 지정합니다. 변수를 선언할 때 변수가 정적 생존 기간을 가지며, 다른 값을 지정하지 않으면 컴파일러가 0으로 초기화합니다.  
  
2.  함수에 변수를 선언하는 경우, `static` 키워드는 해당 함수 호출 간 변수의 상태가 유지되도록 지정합니다.  
  
3.  클래스 선언에서 데이터 멤버를 선언하는 경우, `static`키워드는 멤버의 복사본 하나가 클래스의 모든 인스턴스에 공유되도록 지정합니다. 정적 데이터 멤버는 파일 범위에서 정의되어야 합니다. 로 선언 하는 정수 계열 데이터 멤버 `const static` 는 이니셜라이저를 사용할 수 있습니다.  
  
4.  클래스 선언에서 데이터 멤버를 선언하는 경우, `static` 키워드는 해당 함수가 클래스의 모든 인스턴스에 공유되도록 지정합니다. 정적 멤버 함수는 암시적 `this` 포인터가 없기 때문에 인스턴스 멤버에 액세스할 수 없습니다. 인스턴스 멤버에 액세스하려면 인스턴스 포인터나 참조인 매개 변수로 함수를 선언해야 합니다.  
  
5.  공용 구조체의 멤버는 정적 상태로 선언할 수 없습니다. 하지만 전역으로 선언된 익명 공용 구조체는 `static`으로 명시적으로 선언해야 합니다.  
  
이 예에서는 변수 선언 하는 방법을 보여 줍니다. `static` 함수에서 함수 호출 간에 상태를 유지 합니다.  
  
```cpp  
// static1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
void showstat( int curr ) {  
   static int nStatic;    // Value of nStatic is retained  
                          // between each function call  
   nStatic += curr;  
   cout << "nStatic is " << nStatic << endl;  
}  
  
int main() {  
   for ( int i = 0; i < 5; i++ )  
      showstat( i );  
}  
```  
  
```Output  
nStatic is 0  
nStatic is 1  
nStatic is 3  
nStatic is 6  
nStatic is 10  
```  
  
이 예에서는 사용을 보여 줍니다. `static` 클래스에서 합니다.  
  
```cpp  
// static2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CMyClass {  
public:  
   static int m_i;  
};  
  
int CMyClass::m_i = 0;  
CMyClass myObject1;  
CMyClass myObject2;  
  
int main() {  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject1.m_i = 1;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject2.m_i = 2;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   CMyClass::m_i = 3;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
}  
```  
  
```Output  
0  
0  
1  
1  
2  
2  
3  
3  
```  
  
이 예에서는 선언 된 지역 변수에 `static` 멤버 함수에 있습니다. 정적 변수는 전체 프로그램에서 사용할 수 있으며 해당 형식의 모든 인스턴스는 정적 변수의 동일한 복사본을 공유합니다.  
  
```cpp  
// static3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
struct C {  
   void Test(int value) {  
      static int var = 0;  
      if (var == value)   
         cout << "var == value" << endl;  
      else  
         cout << "var != value" << endl;  
  
      var = value;  
   }  
};   
  
int main() {  
   C c1;  
   C c2;  
   c1.Test(100);  
   c2.Test(100);  
}  
```  
  
```Output  
var != value  
var == value  
```  
  
C++11부터 정적 지역 변수 초기화는 스레드로부터 안전이 보장됩니다. 이 기능은 라고도 *매직 정적 이름*합니다. 그러나 다중 스레드 응용 프로그램에서는 모든 후속 할당을 동기화해야 합니다. 사용 하 여 스레드로부터 안전한 정적 초기화 기능을 해제할 수 있습니다는 [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) CRT에 대 한 종속성을 받지 않도록 하는 플래그입니다.  
  
<a name="extern"></a>  
  
## <a name="extern"></a>extern  
  
`extern`으로 선언된 변수와 개체는 바깥쪽 범위나 다른 변환 단위에 정의된 개체를 외부 링크가 있는 것으로 선언합니다.  
  
선언 `const` 사용 하 여 변수는 `extern` 저장소 클래스 변수 외부 링크를 강제로 수행 합니다. 초기화는 `extern const` 변수 정의 변환 단위에서 허용 됩니다. 정의하는 변환 단위 이외의 변환 단위에서 초기화하면 정의되지 않은 결과가 생성됩니다. 자세한 내용은 참조 [extern 링크 지정을 사용 하 여](../cpp/using-extern-to-specify-linkage.md)  
  
다음 코드에서는 두 가지 `extern` 선언, `DefinedElsewhere`(다른 변환 단위에 정의된 이름을 참조함) 및 `DefinedHere`(포함 범위에 정의된 이름을 참조함)를 보여 줍니다.  
  
```cpp  
// external.cpp  
// DefinedElsewhere is defined in another translation unit  
extern int DefinedElsewhere;     
int main() {  
   int DefinedHere;   
   {  
      // refers to DefinedHere in the enclosing scope  
      extern int DefinedHere;  
   }  
}  
```  
  
<a name="thread_local"></a>  
  
## <a name="threadlocal-c11"></a>thread_local(C++11)  
  
`thread_local` 지정자를 사용하여 선언된 변수는 변수가 생성된 스레드에서만 액세스할 수 있습니다. 변수는 스레드를 만들 때 생성되고 스레드를 삭제할 때 삭제됩니다. 각 스레드에 변수의 자체 복사본이 있습니다. Windows에서는 `thread_local` 기능적으로 Microsoft 특정 [__declspec (thread)](../cpp/thread.md) 특성입니다.  
  
```cpp  
thread_local float f = 42.0; // Global namespace. Not implicitly static.
  
struct S // cannot be applied to type definition  
{  
    thread_local int i; // Illegal. The member must be static.  
    thread_local static char buf[10]; // OK 
};  
  
void DoSomething()  
{  
    // Apply thread_local to a local variable.
    // Implicitly "thread_local static S my_struct".
    thread_local S my_struct;  
}  
```  
  
에 대 한 주의할 점은 `thread_local` 지정자:  
  
-  `thread_local` 지정자와 함께 `static` 또는 `extern`합니다.  
  
-  적용할 수 있습니다 `thread_local` 데이터 선언 및 정의;에 `thread_local` 함수 선언 또는 정의에 사용할 수 없습니다.  
  
-  사용 `thread_local` 방해할 수 있으므로 [지연 로드](../build/reference/linker-support-for-delay-loaded-dlls.md) DLL 가져오기의 합니다. 
  
-  XP 시스템에서는 `thread_local` DLL을 사용 하는 경우 제대로 작동 하지 않을 `thread_local` 고 데이터를 통해 동적으로 로드 되 `LoadLibrary`합니다.  
  
-  정적 저장 기간이 있는 데이터 항목에만 `thread_local`을 지정할 수 있습니다. 여기에 전역 데이터 개체 (둘 다 `static` 및 `extern`), 지역 정적 개체 및 클래스의 정적 데이터 멤버가 있습니다. 모든 지역 변수의 선언 `thread_local` 는 없는 다른 저장소 클래스를 제공 하도록 하는 경우 암시적으로 정적 블록 범위에서 즉, `thread_local` 같습니다 `thread_local static`합니다. 
  
-  스레드 로컬 개체의 선언과 정의가 같은 파일에서 발생하는지, 아니면 별도의 파일에서 발생하는지와 관계없이 해당 선언과 정의 둘 다에 대해 `thread_local`을 지정해야 합니다.  
  
Windows에서는 `thread_local` 기능적으로 [__declspec (thread)](../cpp/thread.md) 점을 제외 하 고 `__declspec(thread)` 형식 정의에 적용 될 수 있으며은 C 코드에서 유효 합니다. 가능한 경우 항상 C++ 표준의 일부로 포팅 가능성이 큰 `thread_local`을 사용합니다.  
  
##  <a name="register"></a>등록  
**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):는 `register` 키워드는 더 이상 지원 되는 저장소 클래스입니다. 키워드는 나중에 사용할 표준에서 계속 예약 되어 있습니다. 

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>예: 자동 정적 초기화와 비교  
  
로컬 자동 개체나 변수는 컨트롤의 흐름이 정의에 도달할 때마다 초기화됩니다. 로컬 정적 개체 또는 변수는 컨트롤의 흐름이 정의에 처음 도달할 때 초기화됩니다.  
  
다음 예제에서는 개체의 초기화 및 개체의 초기화와 소멸을 기록한 후 `I1`, `I2` 및 `I3` 객체를 정의합니다.  
  
```cpp  
// initialization_of_objects.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
using namespace std;  
  
// Define a class that logs initializations and destructions.  
class InitDemo {  
public:  
    InitDemo( const char *szWhat );  
    ~InitDemo();  
  
private:  
    char *szObjName;  
    size_t sizeofObjName;  
};  
  
// Constructor for class InitDemo  
InitDemo::InitDemo( const char *szWhat ) :  
    szObjName(NULL), sizeofObjName(0) {  
    if ( szWhat != 0 && strlen( szWhat ) > 0 ) {  
        // Allocate storage for szObjName, then copy  
        // initializer szWhat into szObjName, using  
        // secured CRT functions.  
        sizeofObjName = strlen( szWhat ) + 1;  
  
        szObjName = new char[ sizeofObjName ];  
        strcpy_s( szObjName, sizeofObjName, szWhat );  
  
        cout << "Initializing: " << szObjName << "\n";  
    }  
    else {  
        szObjName = 0;  
    }
}  
  
// Destructor for InitDemo  
InitDemo::~InitDemo() {  
    if( szObjName != 0 ) {  
        cout << "Destroying: " << szObjName << "\n";  
        delete szObjName;  
    }  
}  
  
// Enter main function  
int main() {  
    InitDemo I1( "Auto I1" ); {  
        cout << "In block.\n";  
        InitDemo I2( "Auto I2" );  
        static InitDemo I3( "Static I3" );  
    }  
    cout << "Exited block.\n";  
}  
```  
  
```Output  
Initializing: Auto I1  
In block.  
Initializing: Auto I2  
Initializing: Static I3  
Destroying: Auto I2  
Exited block.  
Destroying: Auto I1  
Destroying: Static I3  
```  
  
시기와 방법을 보여 주는이 예제 개체 `I1`, `I2`, 및 `I3` 초기화 및 제거 되는 경우.  
  
프로그램에 대해 점이 있습니다.  
  
- 첫째, 제어 흐름이 정의된 블록을 종료할 때 `I1` 및 `I2`가 자동으로 제거됩니다.  
  
- 둘째, C++에서는 블록의 시작 부분에서 개체나 변수를 선언할 필요가 없습니다. 또한 제어 흐름이 정의에 도달해야 이 개체가 초기화됩니다. `I2` 및 `I3`이 그러한 정의의 예입니다. 초기화되면 출력이 정확하게 표시됩니다.  
  
- 마지막으로 `I3`과 같은 정적 지역 변수는 프로그램 지속 시간 동안 값을 보유하지만 프로그램이 종료되면 제거됩니다.  
  
## <a name="see-also"></a>참고 항목  
  
 [선언 및 정의](../cpp/declarations-and-definitions-cpp.md)

