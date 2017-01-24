---
title: "저장소 클래스(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "thread_local_cpp"
  - "external_cpp"
  - "static_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "저장소 클래스, 기본 개념"
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 저장소 클래스(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 변수 선언 컨텍스트에서 *저장소 클래스*는 개체의 수명, 링크 및 메모리 위치를 제어하는 형식 지정자입니다.  주어진 개체에는 저장소 클래스가 하나만 있을 수 있습니다.  `extern`, `static`또는 `thread_local` 지정자를 사용하여 달리 지정되지 않은 경우 블록 내에 정의된 변수는 자동 저장소를 갖습니다.  자동 개체 및 변수는 링크가 없으며 블록 외부의 코드에 표시되지 않습니다.  
  
 **노트**  
  
1.  [mutable](../cpp/mutable-data-members-cpp.md) 키워드는 저장소 클래스 지정자로 간주될 수 있습니다.  하지만 클래스 정의의 멤버 목록에만 사용할 수 있습니다.  
  
2.  [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)]부터 `auto` 키워드는 더 이상 C\+\+ 저장소 클래스 지정자가 아니며 `register` 키워드는 사용되지 않습니다.  
  
-   [정적](#static)  
  
-   [extern](#extern)  
  
-   [thread\_local](#thread_local)  
  
## 정적  
 `static` 키워드는 전역 범위, 네임스페이스 범위 및 클래스 범위에서 변수와 함수를 선언하는 데 사용할 수 있습니다.  정적 변수는 로컬 범위에서 선언할 수도 있습니다.  
  
 정적 생존 기간이란 프로그램이 시작될 때 개체 또는 변수가 할당되고 프로그램이 끝날 때 개체 또는 변수가 할당 취소됨을 의미합니다.  외부 연결은 변수가 선언된 파일 외부에서 변수 이름이 표시됨을 의미합니다.  반대로 내부 연결은 변수가 선언된 파일 외부에 이름이 표시되지 않음을 의미합니다.  기본적으로 전역 네임스페이스에서 정의된 개체 또는 변수에는 정적 지속 기간 및 외부 링크가 있습니다.  `static` 키워드는 다음 상황에서 사용할 수 있습니다.  
  
1.  파일 범위\(전역 및\/또는 네임스페이스 범위\)에 변수 또는 함수를 선언한 경우, `static` 키워드는 변수 또는 함수에 내부 링크가 있음을 지정합니다.  변수를 선언할 때 변수가 정적 생존 기간을 가지며, 다른 값을 지정하지 않으면 컴파일러가 0으로 초기화합니다.  
  
2.  함수에 변수를 선언하는 경우, `static` 키워드는 해당 함수 호출 간 변수의 상태가 유지되도록 지정합니다.  
  
3.  클래스 선언에서 데이터 멤버를 선언하는 경우, `static`키워드는 멤버의 복사본 하나가 클래스의 모든 인스턴스에 공유되도록 지정합니다.  정적 데이터 멤버는 파일 범위에서 정의되어야 합니다.  `const` `static`으로 선언되는 정수 계열 데이터 멤버는 이니셜라이저를 가질 수 있습니다.  
  
4.  클래스 선언에서 데이터 멤버를 선언하는 경우, `static` 키워드는 해당 함수가 클래스의 모든 인스턴스에 공유되도록 지정합니다.  정적 멤버 함수는 암시적 `this` 포인터가 없기 때문에 인스턴스 멤버에 액세스할 수 없습니다.  인스턴스 멤버에 액세스하려면 인스턴스 포인터나 참조인 매개 변수로 함수를 선언해야 합니다.  
  
5.  공용 구조체의 멤버는 정적 상태로 선언할 수 없습니다.  하지만 전역으로 선언된 익명 공용 구조체는 `static`으로 명시적으로 선언해야 합니다.  
  
 다음 예제에서는 함수에서 선언된 `static` 변수가 해당 함수 호출 간에 상태를 유지하는 방법을 보여 줍니다.  
  
```  
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
  
  **nStatic은 0입니다.**  
**nStatic is 1**  
**nStatic is 3**  
**nStatic is 6**  
**nStatic is 10** 다음 예제에서는 `static`을 클래스에서 사용하는 방법을 보여 줍니다.  
  
```  
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
  
  **0**  
**0**  
**1**  
**1**  
**2**  
**2**  
**3**  
**3** 다음 예제에서는 멤버 함수에서 `static`으로 선언된 지역 변수를 보여 줍니다.  정적 변수는 전체 프로그램에서 사용할 수 있으며 해당 형식의 모든 인스턴스는 정적 변수의 동일한 복사본을 공유합니다.  
  
```  
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
  
  **var \!\= value**  
**var \=\= value** C\+\+11부터 정적 지역 변수 초기화는 스레드로부터 안전이 보장됩니다.  이 기능을 *매직 정적 이름*이라고도 합니다.  그러나 다중 스레드 응용 프로그램에서는 모든 후속 할당을 동기화해야 합니다.  CRT에 대한 종속성 사용을 방지하기 위해 \/Zc:threadSafeInit\- 플래그를 사용하여 스레드로부터 안전한 정적 기능을 사용하지 않도록 설정할 수 있습니다.  
  
## extern  
 `extern`으로 선언된 변수와 개체는 바깥쪽 범위나 다른 변환 단위에 정의된 개체를 외부 링크가 있는 것으로 선언합니다.  
  
 **저장소 클래스를 사용하여 `extern`const** 변수를 선언하면 해당 변수가 외부 링크를 갖게 됩니다.  **extern const** 변수의 초기화는 정의하는 변환 단위에서 허용됩니다.  정의하는 변환 단위 이외의 변환 단위에서 초기화하면 정의되지 않은 결과가 생성됩니다.  자세한 내용은 [extern을 사용하여 링크 지정](../cpp/using-extern-to-specify-linkage.md)을 참조하세요.  
  
 다음 코드에서는 두 가지 `extern` 선언, `DefinedElsewhere`\(다른 변환 단위에 정의된 이름을 참조함\) 및 `DefinedHere`\(포함 범위에 정의된 이름을 참조함\)를 보여 줍니다.  
  
```  
// external.cpp  
// defined in another translation unit  
extern int DefinedElsewhere;     
int main() {  
   int DefinedHere;   
   {  
      // refers to DefinedHere in the enclosing scope  
      extern int DefinedHere;  
    }  
}  
```  
  
## thread\_local\(C\+\+11\)  
 `thread_local` 지정자를 사용하여 선언된 변수는 변수가 생성된 스레드에서만 액세스할 수 있습니다.  변수는 스레드를 만들 때 생성되고 스레드를 삭제할 때 삭제됩니다.  각 스레드에 변수의 자체 복사본이 있습니다.  Windows에서 `thread_local`은 Microsoft 특정 [\_\_declspec\(thread\)](../cpp/thread.md) 특성과 기능이 같습니다.  
  
```  
thread_local float f = 42.0; //global namespace  
  
struct C // cannot be applied to type definition  
{  
thread_local int i; //local  
thread_local static char buf[10]; // local and static  
};  
  
void DoSomething()  
{  
thread_local C my_struct; // Apply  thread_local to a variable  
}  
```  
  
1.  thread\_local 지정자를 `static` 또는 `extern`과 함께 사용할 수 있습니다.  
  
2.  데이터 선언 및 정의에만 `thread_local`을 적용할 수 있습니다. **thread\_local**은 함수 선언 또는 정의에 사용할 수 없습니다.  
  
3.  `thread_local` 사용은 DLL 가져오기의 [지연 로드](../build/reference/linker-support-for-delay-loaded-dlls.md)를 방해할 수 있습니다**.**  
  
4.  XP 시스템에서는 DLL이 `thread_local` 데이터를 사용하고 LoadLibrary를 통해 동적으로 로드되는 경우 `thread_local`가 올바르게 작동하지 않을 수 있습니다.  
  
5.  정적 저장 기간이 있는 데이터 항목에만 `thread_local`을 지정할 수 있습니다.  여기에는 전역 데이터 개체\(**static** 및 `extern`\), 지역 정적 개체 및 클래스의 정적 데이터 멤버가 포함됩니다.  자동 데이터 개체는 **thread\_local**을 사용하여 선언할 수 없습니다.  
  
6.  스레드 로컬 개체의 선언과 정의가 같은 파일에서 발생하는지, 아니면 별도의 파일에서 발생하는지와 관계없이 해당 선언과 정의 둘 다에 대해 `thread_local`을 지정해야 합니다.  
  
 Windows에서 `thread_local`은 형식 정의에 \_\_declspec\(thread\)를 적용할 수 있고 C 코드에서 유효하다는 점을 제외하고 [\_\_declspec\(thread\)](../cpp/thread.md)와 기능이 같습니다.  가능한 경우 항상 C\+\+ 표준의 일부로 포팅 가능성이 큰 `thread_local`을 사용합니다.  
  
 자세한 내용은 [TLS](../parallel/thread-local-storage-tls.md)를 참조하세요.  
  
## register  
 C\+\+11에서는 **register** 키워드가 사용되지 않습니다.  이 키워드는 가능한 경우 변수를 컴퓨터 레지스터에 저장하도록 지정합니다.  함수 인수 및 지역 변수만 레지스터 저장소 클래스를 사용하여 선언할 수 있습니다.  
  
```  
register int num;  
```  
  
 자동 변수와 마찬가지로 레지스터 변수는 해당 변수가 선언된 블록의 끝까지만 지속됩니다.  
  
 컴파일러는 레지스터 변수에 대한 사용자 요청을 고려하지 않습니다. 대신 전역 최적화가 설정된 경우 자체적으로 레지스터를 선택합니다.  하지만 [register](http://msdn.microsoft.com/ko-kr/5b66905a-2f7f-4918-bb55-5e66d4bc50f9) 키워드와 연결된 다른 모든 의미 체계는 컴파일러에서 적용됩니다.  
  
 연산자\(**&**\) 주소가 레지스터를 사용하여 선언된 개체에서 사용된 경우 컴파일러는 레지스터 대신 메모리에 개체를 넣어야 합니다.  
  
## 예: 자동 및정적 초기화  
 로컬 자동 개체나 변수는 컨트롤의 흐름이 정의에 도달할 때마다 초기화됩니다.  로컬 정적 개체 또는 변수는 컨트롤의 흐름이 정의에 처음 도달할 때 초기화됩니다.  
  
 다음 예제에서는 개체의 초기화 및 개체의 초기화와 소멸을 기록한 후 `I1`, `I2` 및 `I3` 객체를 정의합니다.  
  
```  
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
   if( szWhat != 0 && strlen( szWhat ) > 0 ) {  
      // Allocate storage for szObjName, then copy  
      // initializer szWhat into szObjName, using  
      // secured CRT functions.  
      sizeofObjName = strlen( szWhat ) + 1;  
  
      szObjName = new char[ sizeofObjName ];  
      strcpy_s( szObjName, sizeofObjName, szWhat );  
  
      cout << "Initializing: " << szObjName << "\n";  
   }  
   else  
      szObjName = 0;  
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
  
  **Initializing: Auto I1**  
**In block.  Initializing: Auto I2**  
**Initializing: Static I3**  
**Destroying: Auto I2**  
**Exited block.  Destroying: Auto I1**  
**Destroying: Static I3**  이전의 코드에서는 `I1`, `I2` 및 `I3` 개체가 초기화되는 방법과 시기 및 삭제되는 시기를 보여 줍니다.  
  
 프로그램에 대해 여러 가지 유의할 사항이 있습니다.  
  
 첫째, 제어 흐름이 정의된 블록을 종료할 때 `I1` 및 `I2`가 자동으로 제거됩니다.  
  
 둘째, C\+\+에서는 블록의 시작 부분에서 개체나 변수를 선언할 필요가 없습니다.  또한 제어 흐름이 정의에 도달해야 이 개체가 초기화됩니다.  `I2` 및 `I3`이 그러한 정의의 예입니다. 초기화되면 출력이 정확하게 표시됩니다.  
  
 마지막으로 `I3`과 같은 정적 지역 변수는 프로그램 지속 시간 동안 값을 보유하지만 프로그램이 종료되면 제거됩니다.  
  
## 참고 항목  
 [선언 및 정의](../cpp/declarations-and-definitions-cpp.md)