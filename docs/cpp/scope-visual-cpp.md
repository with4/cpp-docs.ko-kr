---
title: "범위 (Visual c + +) | Microsoft Docs"
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
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3502a16c0cbbccdfd5d73aafe776d907c9845c1f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="scope-visual-c"></a>범위(Visual C++)
프로그램의 특정 영역에서만 C++를 사용할 수 있습니다. 이 영역을 이름의 "범위"라고 합니다. 범위는 정적 범위의 개체가 표시되지 않는 이름의 "수명"을 결정합니다. 클래스 생성자와 소멸자가 호출되고 범위에 로컬인 변수가 초기화되면 범위가 이름의 표시 유형을 결정하기도 합니다. (자세한 내용은 참조 [생성자](../cpp/constructors-cpp.md) 및 [소멸자](../cpp/destructors-cpp.md).) 범위의 종류는 다음 5가지입니다.  
  
-   **로컬 범위** 블록 내에서 선언 된 이름은 해당 블록과에서 및 선언 시점 이후 묶인 내 에서만 액세스할 수 있습니다. 함수 본문 바깥쪽 범위 안에서 선언된 것처럼 가장 바깥쪽 함수 블록의 범위에서 함수의 정식 인수 이름에 로컬 범위가 포함됩니다. 다음과 같은 코드 조각을 생각해 봅시다.  
  
    ```  
    {  
        int i;  
    }  
    ```  
  
     `i`가 중괄호 안의 블록에 선언되었으므로 `i`에 로컬 범위가 있으며 액세스할 수 없습니다. 중괄호를 닫기 전에는 코드가 액세스할 수 없기 때문입니다.  
  
-   **함수 범위** 레이블은 함수 범위가 있는 유일한 이름은 다음과 같습니다. 함수 안의 어디에나 사용할 수 있지만 해당 함수 밖에서 액세스할 수는 없습니다. 함수에 대한 형식 인수(함수 정의에서 지정)는 함수 본문의 바깥쪽 블록의 범위에 있는 것으로 간주됩니다.  
  
-   **파일 범위** 모든 블록이 나 클래스 외부에 선언 된 이름에는 파일 범위가 있습니다. 선언 후에는 변환 단위 어디에서나 액세스할 수 있습니다 파일 범위가 정적 개체를 선언하지 않는 이름을 전역 이름이라고 합니다.  
  
     C++에서는 파일 범위를 네임스페이스 범위라고도 합니다.  
  
-   **클래스 범위** 클래스 멤버의 이름을 클래스 범위를 가집니다. 클래스 멤버 함수는 멤버 선택 연산자를 사용 하 여 액세스할 수 있습니다 (**합니다.** 또는 ** -> **) 또는 멤버 포인터 연산자 (**.\* ** 또는 ** -> \* **) 개체나; 해당 클래스의 개체에 대 한 포인터에 비정적 클래스 멤버 데이터 해당 클래스의 개체에 로컬 간주 됩니다. 다음과 같은 클래스 선언을 생각해 보세요.  
  
    ```  
    class Point  
    {  
        int x;  
        int y;  
    };  
    ```  
  
     클래스 멤버 `x` 및 `y`는 `Point` 클래스의 범위에 있다고 간주됩니다.  
  
-   **프로토타입 범위** 함수 프로토타입을에 선언 된 이름은 프로토타입 끝 까지만 표시 됩니다. 다음 프로토타입은 이름 3개(`strDestination`, `numberOfElements` 및 `strSource`)를 선언하며 이 이름은 프로토타입 끝에서 범위를 벗어납니다.  
  
    ```  
    errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
    ```  
  
## <a name="hiding-names"></a>이름 숨기기  
 이름을 포함된 블록에서 선언하여 숨길 수 있습니다. 다음 그림에서는 `i`가 내부 블록 안에서 다시 선언되므로 바깥쪽 블록 범위에서 `i`와 연결된 변수가 숨겨집니다.  
  
 ![블록 &#45; 범위 이름 숨기기](../cpp/media/vc38sf1.png "vc38SF1")  
블록 범위 및 이름 숨기기  
  
 그림에 표시된 프로그램의 출력은 다음과 같습니다.  
  
```  
i = 0  
i = 7  
j = 9  
i = 0  
```  
  
> [!NOTE]
>  `szWhat` 인수는 함수 범위에 있는 것으로 간주되므로 함수의 가장 바깥쪽 블록에서 선언된 것처럼 취급됩니다.  
  
## <a name="hiding-class-names"></a>클래스 이름 숨기기  
 함수, 개체, 변수 또는 열거자를 동일한 코드에서 선언하여 클래스 이름을 숨길 수 있습니다. 그러나 클래스 이름에 액세스할 수 있습니다 키워드가 접두사로 붙는 경우 **클래스**합니다.  
  
```  
// hiding_class_names.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
// Declare class Account at file scope.  
class Account  
{  
public:  
    Account( double InitialBalance )  
        { balance = InitialBalance; }  
    double GetBalance()  
        { return balance; }  
private:  
    double balance;  
};  
  
double Account = 15.37;            // Hides class name Account  
  
int main()  
{  
    class Account Checking( Account ); // Qualifies Account as   
                                       //  class name  
  
    cout << "Opening account with balance of: "  
         << Checking.GetBalance() << "\n";  
}  
//Output: Opening account with balance of: 15.37  
```  
  
> [!NOTE]
>  클래스 이름(`Account`)이 호출되는 모든 위치에서 파일 범위 변수 Account와 구별하기 위해 class 키워드를 사용해야 합니다. 이 규칙은 범위 결정 연산자(::)의 왼쪽에 클래스 이름이 나타나는 경우에는 적용되지 않습니다. 범위 결정 연산자의 왼쪽에 있는 이름은 항상 클래스 이름으로 간주됩니다.  
  
 다음 예제에서는 형식의 개체에 대 한 포인터를 선언 하는 방법을 `Account` 를 사용 하 여 **클래스** 키워드:  
  
```  
class Account *Checking = new class Account( Account );  
```  
  
 `Account` 앞의 문에서 괄호 안에 이니셜라이저에는 파일 범위가 있으며 유형은 **double**합니다.  
  
> [!NOTE]
>  이 예제와 같이 식별자 이름을 다시 사용하는 것은 좋지 않은 프로그래밍 스타일로 간주됩니다.  
  
 포인터에 대 한 자세한 내용은 참조 [파생 형식](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c)합니다. 클래스 개체의 선언 및 초기화에 대 한 정보를 참조 하십시오. [클래스, 구조체 및 공용 구조체](../cpp/classes-and-structs-cpp.md)합니다. 사용 하는 방법에 대 한 내용은 **새** 및 **삭제** 가능한 저장소 연산자, 참조 [새 및 delete 연산자](new-and-delete-operators.md)합니다.  
  
## <a name="hiding-names-with-file-scope"></a>파일 범위가 있는 이름 숨기기  
 블록 범위에 같은 이름을 명시적으로 선언하여 파일 범위와 함께 이름을 숨길 수 있습니다. 그러나 범위 결정 연산자(`::`)를 사용하여 파일 범위 이름에 액세스할 수 있습니다.  
  
```  
// file_scopes.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int i = 7;   // i has file scope, outside all blocks  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   int i = 5;   // i has block scope, hides i at file scope  
   cout << "Block-scoped i has the value: " << i << "\n";  
   cout << "File-scoped i has the value: " << ::i << "\n";  
}  
```  
  
```Output  
Block-scoped i has the value: 5  
File-scoped i has the value: 7  
```  
  
## <a name="see-also"></a>참고 항목  
 [기본 개념](../cpp/basic-concepts-cpp.md)
