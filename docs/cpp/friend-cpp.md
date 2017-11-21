---
title: friend (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: friend_cpp
dev_langs: C++
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b30b49825d14e72c06f569c343f96c7cf091a62f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="friend-c"></a>friend (C++)
이 경우에 따라 개별 클래스의 모든 멤버 또는 클래스의 멤버가 아닌 함수에 멤버 수준 액세스 권한을 부여할 간편 합니다. 클래스 구현자만 이 클래스의 friend를 선언할 수 있습니다. 함수 또는 클래스는 자신을 클래스의 friend로 선언할 수 없습니다. 클래스 정의에서 사용 된 `friend` 키워드 및 비멤버 함수 또는 클래스의 private 컨트롤과 protected 멤버에 액세스 권한을 부여 다른 클래스의 이름입니다.         템플릿 정의에 형식 매개 변수는 friend로 선언할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class friend F  
friend F;  
```  
  
## <a name="friend-declarations"></a>Friend 선언  
 이전에 선언되지 않은 friend 함수를 선언하는 경우 해당 함수가 바깥쪽 비클래스 범위로 내보내집니다.  
  
 friend 선언에서 선언된 함수는 `extern` 키워드를 사용하여 선언된 것처럼 취급됩니다. (에 대 한 자세한 내용은 `extern`, 참조 [정적 저장소 클래스 지정자](http://msdn.microsoft.com/en-us/3ba9289a-a412-4a17-b319-ceb2c087df48).)  
  
 전역 범위를 갖는 함수는 프로토타입 이전에 friend로 선언될 수 있지만, 멤버 함수는 전체 클래스 선언이 나타나기 전에 friend로 선언될 수 없습니다. 다음 코드에서는 이러한 작업이 실패하는 이유를 보여 줍니다.  
  
```cpp  
class ForwardDeclared;   // Class name is known.  
class HasFriends  
{  
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected  
};  
```  
  
 위의 예제에서는 클래스 이름 `ForwardDeclared`를 범위에 입력하지만, 전체 선언(특히 `IsAFriend` 함수를 선언하는 부분)은 알 수 없습니다. 따라서 `friend` 클래스의 `HasFriends` 선언은 오류를 생성합니다.  
  
 C + + 11부터는 클래스에 대 한 friend 선언의 두 가지 형식이 있습니다.  
  
```cpp  
friend class F;  
friend F;  
```  
  
 첫 번째 형태는 가장 안쪽의 네임 스페이스에 해당 이름의 기존 클래스가 없는 경우 새 클래스 F를 소개 합니다.  **C + + 11**: 두 번째 형태는 새 클래스를 사용 하지 않습니다; 클래스에 선언 된 템플릿 형식 매개 변수 또는 형식 정의 friend로 선언할 때 사용 해야 하는 경우 사용 될 수 있습니다.  
  
 사용 하 여 `class friend F` 때 참조 된 형식 선언 되지 않은 아직:  
  
```cpp  
namespace NS  
{  
    class M  
    {  
        class friend F;  // Introduces F but doesn't define it  
    };  
}  
```  
  
```cpp  
namespace NS  
{  
    class M  
    {  
        friend F; // error C2433: 'NS::F': 'friend' not permitted on data declarations  
    };  
}  
```  
  
 다음 예에서 `friend F` 참조 하는 `F` NS 범위 밖에 서 선언 된 클래스입니다.  
  
```cpp  
class F {};  
namespace NS  
{  
    class M  
    {  
        friend F;  // OK   
    };  
}  
```  
  
 사용 하 여 `friend F` friend로는 템플릿 매개 변수를 선언 하려면:  
  
```cpp  
template <typename T>  
class my_class  
{  
    friend T;  
    //...  
};  
```  
  
 사용 하 여 `friend F` typedef friend로 선언할 수 있습니다.  
  
```cpp  
class Foo {};  
typedef Foo F;  
  
class G  
{  
    friend F; // OK  
    friend class F // Error C2371 -- redefinition  
};  
```  
  
 서로 friend인 두 클래스를 선언하려면 두 번째 클래스 전체가 첫 번째 클래스의 friend로 지정되어야 합니다. 이러한 제한은 컴파일러가 두 번째 클래스가 선언된 지점에서만 개별 friend 함수를 선언하는 데 충분한 정보를 갖기 때문에 발생합니다.  
  
> [!NOTE]
>  두 번째 클래스 전체가 첫 번째 클래스의 friend여야 하지만, 두 번째 클래스의 friend가 될 첫 번째 클래스의 함수를 선택할 수 있습니다.  
  
## <a name="friend-functions"></a>friend 함수  
 `friend` 함수는 클래스의 멤버가 아니지만 클래스의 전용 및 보호된 멤버에 액세스할 수 있는 함수입니다. friend 함수는 클래스 멤버로 간주되지 않으며, 특수 액세스 권한이 부여된 일반 외부 함수입니다. Friend 클래스의 범위에 있지 않은 한 멤버 선택 연산자를 사용 하 여 호출 되지 않습니다 (**합니다.** 매개 변수와-**>**) 다른 클래스의 멤버가 아닌 합니다. `friend` 함수는 액세스 권한을 부여하는 클래스에서 선언됩니다. `friend` 선언은 클래스 선언의 어느 곳에나 배치될 수 있으며, 액세스 제어 키워드의 영향을 받지 않습니다.  
  
 다음 예제에서는 `Point` 클래스와 `ChangePrivate`라는 friend 함수를 보여 줍니다. `friend` 함수는 매개 변수로 받는 `Point` 개체의 전용 데이터 멤버에 액세스할 수 있습니다.  
  
```cpp  
// friend_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
    friend void ChangePrivate( Point & );  
public:  
    Point( void ) : m_i(0) {}  
    void PrintPrivate( void ){cout << m_i << endl; }  
  
private:  
    int m_i;  
};  
  
void ChangePrivate ( Point &i ) { i.m_i++; }  
  
int main()  
{  
   Point sPoint;  
   sPoint.PrintPrivate();  
   ChangePrivate(sPoint);  
   sPoint.PrintPrivate();  
// Output: 0  
           1  
}  
```  
  
## <a name="class-members-as-friends"></a>Friend 클래스 멤버  
 클래스 멤버 함수는 다른 클래스에서 friend로 선언될 수 있습니다. 다음 예제를 참조하세요.  
  
```cpp  
// classes_as_friends1.cpp  
// compile with: /c  
class B;  
  
class A {  
public:  
   int Func1( B& b );  
  
private:  
   int Func2( B& b );  
};  
  
class B {  
private:  
   int _b;  
  
   // A::Func1 is a friend function to class B  
   // so A::Func1 has access to all members of B  
   friend int A::Func1( B& );  
};  
  
int A::Func1( B& b ) { return b._b; }   // OK  
int A::Func2( B& b ) { return b._b; }   // C2248  
```  
  
 위의 예제에서는 `A::Func1( B& )` 함수에만 `B` 클래스에 대한 friend 액세스 권한이 부여됩니다. 따라서 전용 멤버에 대 한 액세스 `_b` 올바른지 `Func1` 클래스의 `A` 아니라 `Func2`합니다.  
  
 `friend` 클래스는 모든 멤버 함수가 클래스의 friend 함수인 클래스입니다. 즉, 멤버 함수가 다른 클래스의 전용 및 보호된 멤버에 액세스할 수 있습니다. `friend` 클래스의 `B` 선언이 다음과 같다고 가정합니다.  
  
```cpp  
friend class A;  
```  
  
 이 경우 `A` 클래스의 모든 멤버 함수에 `B` 클래스에 대한 freind 액세스 권한이 부여되었습니다. 다음 코드는 friend 클래스의 예입니다.  
  
```cpp  
// classes_as_friends2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class YourClass {  
friend class YourOtherClass;  // Declare a friend class  
public:  
   YourClass() : topSecret(0){}  
   void printMember() { cout << topSecret << endl; }  
private:  
   int topSecret;  
};  
  
class YourOtherClass {  
public:  
   void change( YourClass& yc, int x ){yc.topSecret = x;}  
};  
  
int main() {  
   YourClass yc1;  
   YourOtherClass yoc1;  
   yc1.printMember();  
   yoc1.change( yc1, 5 );  
   yc1.printMember();  
}  
```  
  
 friendship은 이와 같이 명시적으로 지정되지 않은 경우 상호적이 아닙니다. 위의 예제에서 `YourClass`의 멤버 함수는 `YourOtherClass`의 전용 멤버에 액세스할 수 없습니다.  
  
 관리되는 형식에는 friend 함수, friend 클래스 또는 friend 인터페이스가 있을 수 없습니다.  
  
 friendship은 상속되지 않습니다. 즉, `YourOtherClass`에서 파생 클래스는 `YourClass`의 전용 멤버에 액세스할 수 없습니다. friendship은 전이적이 아니므로 `YourOtherClass`의 friend인 클래스는 `YourClass`의 전용 멤버에 액세스할 수 없습니다.  
  
 다음 그림에서는 `Base`, `Derived`, `aFriend` 및 `anotherFriend`라는 네 가지 클래스 선언을 보여 줍니다. `aFriend` 클래스만 `Base` 전용 멤버(및 `Base`에서 상속했을 수 있는 모든 멤버)에 직접 액세스할 수 있습니다.  
  
 ![친구 관계의 의미](../cpp/media/vc38v41.gif "vc38V41")  
friend 관계의 의미  
  
## <a name="inline-friend-definitions"></a>인라인 friend 정의  
 클래스 선언 안에 friend 함수를 정의할 수 있습니다. 이러한 함수는 인라인 함수이며 멤버 인라인 함수와 같이 클래스 범위가 닫히기 전에(클래스 선언의 종료) 모든 클래스 멤버가 표시된 이후 즉시 정의되도록 동작합니다.  
  
 클래스 선언 내에 정의된 friend 함수는 바깥쪽 클래스가 아닌 파일 범위에 있는 것으로 간주됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)