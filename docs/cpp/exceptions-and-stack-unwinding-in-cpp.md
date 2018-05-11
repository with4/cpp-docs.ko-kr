---
title: 예외 및 스택 해제 c + +에서 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b05b2f6240876540cd9e67d83bcb88242b68827b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++에서 예외 및 스택 해제
C++ 예외 메커니즘에서 컨트롤은 throw 문에서 throw된 형식을 처리할 수 있는 첫 번째 catch 문으로 이동합니다. 로 알려진 프로세스에서 삭제 하 catch 문이 도달 하면 모든 자동 변수는 throw 사이의 범위 및 catch 문 *스택 해제*합니다. 스택 해제에서 실행은 다음과 같이 진행됩니다.  
  
1.  제어는 일반 순차적 실행으로 `try` 문에 도달합니다. `try` 블록의 보호된 섹션이 실행됩니다.  
  
2.  보호된 섹션을 실행하는 동안 예외가 throw되지 않는 경우 `catch` 블록 다음에 오는 `try` 절은 실행되지 않습니다. 연결된 `catch` 블록 다음에 오는 마지막 `try` 절 뒤에 있는 문에서 계속 실행됩니다.  
  
3.  보호된 섹션의 실행 중 또는 보호된 섹션이 직접 또는 간접적으로 호출하는 임의의 루틴에서 예외가 throw될 경우 `throw` 피연산자가 만든 개체에서 예외 개체가 만들어집니다. 이는 복사 생성자가 관련될 수 있음을 의미합니다. 이 지점에서 컴파일러는 throw된 형식의 예외를 처리할 수 있는 더 높은 실행 컨텍스트 또는 모든 예외 형식을 처리할 수 있는 `catch` 처리기에서 `catch` 절을 검색합니다. `catch` 처리기는 `try` 블록 다음에 오는 모양의 순서대로 검사됩니다. 적절한 처리기가 발견되지 않으면 바로 다음 바깥쪽 `try` 블록을 검사합니다. 이 프로세스는 가장 바깥쪽 `try` 블록이 검사될 때까지 계속됩니다.  
  
4.  일치하는 처리기를 여전히 찾을 수 없거나 해제 프로세스 중 처리기가 컨트롤을 갖기 전에 예외가 발생하는 경우 미리 정의된 런타임 함수 `terminate`가 호출됩니다. 예외가 throw되었지만 해제 작업을 시작하기 전에 예외가 발생하는 경우 `terminate`가 호출됩니다.  
  
5.  일치하는 `catch` 처리기가 검색되고 이 처리기가 값으로 catch되는 경우 해당 정식 매개 변수는 예외 개체를 복사하여 초기화됩니다. 참조로 catch하면 예외 개체를 참조하도록 매개 변수가 초기화됩니다. 정식 매개 변수가 초기화된 후 스택 해제 프로세스가 시작됩니다. 이는 `try` 처리기와 관련 있는 `catch` 블록의 시작과 예외의 throw 사이트 사이에서 완전히 생성되었으나 아직 소멸되지 않은 모든 자동 개체의 소멸과 관련이 있습니다. 소멸은 생성과 반대 순서로 발생합니다. `catch` 처리기가 실행되고 프로그램은 마지막 처리기 즉, `catch` 처리기가 아닌 첫 번째 문 또는 구문 다음에 실행을 다시 시작합니다. 제어는 `catch` 문의 `goto` 레이블 또는 `case` 문이 아닌 throw된 예외를 통해서만 `switch` 처리기에 들어올 수 있습니다.  
  
## <a name="stack-unwinding-example"></a>스택 해제 예제  
 다음 예제에서는 예외가 throw되면 어떻게 스택이 해제되는지 보여 줍니다. 스레드에서의 실행은 방식에 따라 각 함수를 해제하면서 `C`의 throw 문에서 `main`의 catch 문으로 점프합니다. `Dummy` 개체가 만들어진 다음 범위에서 벗어날 때 소멸되는 순서를 살펴보십시오. 또한 catch 문이 포함된 `main`을 제외하고는 어떤 함수도 완료할 수 없습니다. 함수 `A`는 `B()` 호출에서 반환되지 않으며 `B`도 `C()` 호출에서 반환되지 않습니다. `Dummy` 포인터의 정의 및 해당 delete 문에 대한 주석 처리를 제거한 다음 프로그램을 실행하면 포인터가 삭제되지 않습니다. 이는 함수가 예외 보장을 제공하지 않는 경우 발생할 수 있음을 보여 줍니다. 자세한 내용은 방법: 예외 디자인을 참조하십시오. catch 문을 주석으로 처리하는 경우 처리되지 않은 예외로 인해 프로그램을 종료할 때 나타나는 현상을 확인할 수 있습니다.  
  
```  
#include <string>  
#include <iostream>  
using namespace std;  
  
class MyException{};  
class Dummy  
{  
    public:  
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }  
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }  
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }  
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }  
    string MyName;   
    int level;  
};  
  
void C(Dummy d, int i)  
{   
    cout << "Entering FunctionC" << endl;  
    d.MyName = " C";  
    throw MyException();     
  
    cout << "Exiting FunctionC" << endl;  
}  
  
void B(Dummy d, int i)  
{  
    cout << "Entering FunctionB" << endl;  
    d.MyName = "B";  
    C(d, i + 1);     
    cout << "Exiting FunctionB" << endl;   
}  
  
void A(Dummy d, int i)  
{   
    cout << "Entering FunctionA" << endl;  
    d.MyName = " A" ;  
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!  
    B(d, i + 1);  
 //   delete pd;   
    cout << "Exiting FunctionA" << endl;     
}  
  
int main()  
{  
    cout << "Entering main" << endl;  
    try  
    {  
        Dummy d(" M");  
        A(d,1);  
    }  
    catch (MyException& e)  
    {  
        cout << "Caught an exception of type: " << typeid(e).name() << endl;  
    }  
  
    cout << "Exiting main." << endl;  
    char c;  
    cin >> c;  
}  
  
/* Output:  
    Entering main  
    Created Dummy: M  
    Copy created Dummy: M  
    Entering FunctionA  
    Copy created Dummy: A  
    Entering FunctionB  
    Copy created Dummy: B  
    Entering FunctionC  
    Destroyed Dummy: C  
    Destroyed Dummy: B  
    Destroyed Dummy: A  
    Destroyed Dummy: M  
    Caught an exception of type: class MyException  
    Exiting main.  
  
*/  
  
```