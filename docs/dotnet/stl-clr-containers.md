---
title: "STL/CLR 컨테이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1b8aa8ef5b1425d4aa41b1811dca5ec5d56acd1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-containers"></a>STL/CLR 컨테이너
STL/CLR 라이브러리에 c + + 표준 라이브러리에 있는 동일한 컨테이너가 하지만.NET Framework의 관리 되는 환경 내에서 실행 합니다. C + + 표준 라이브러리에 익숙한 경우 STL/CLR 계속 공용 언어 런타임 (CLR) 대상에 코드를 업그레이드 하는 동안 미리 만들어 둔 기술을 사용 하는 가장 좋은 방법은 됩니다.  
  
 이 문서는 유형의 요소는 컨테이너에 삽입할 수 있습니다 및 소유권 문제는 컨테이너의 요소를 컨테이너 요소에 대 한 요구 사항 등의 STL/CLR 컨테이너에 대 한 개요를 제공 합니다. 적절 한 경우 네이티브 c + + 표준 라이브러리 및 STL/CLR 간의 차이점 설명 합니다.  
  
## <a name="requirements-for-container-elements"></a>컨테이너 요소에 대한 요구 사항  
 C + + 표준 라이브러리 컨테이너에 삽입 하는 모든 요소는 특정 지침을 준수 해야 합니다. 자세한 내용은 참조 [STL/CLR 컨테이너 요소에 대 한 요구 사항을](../dotnet/requirements-for-stl-clr-container-elements.md)합니다.  
  
## <a name="valid-container-elements"></a>유효한 컨테이너 요소  
 STL/CLR 컨테이너 요소 두 유형 중 하나를 보유할 수 있습니다.  
  
-   참조 형식에 처리 합니다.  
  
-   참조 형식.  
  
-   Unboxed 값 형식입니다.  
  
 Boxed 값 형식 STL/CLR 컨테이너의 모든 코드를 삽입할 수 없습니다.  
  
### <a name="handles-to-reference-types"></a>참조 형식에 대 한 핸들  
 STL/CLR 컨테이너에는 참조 형식에 대 한 핸들을 삽입할 수 있습니다. CLR을 대상으로 하는 c + +에 대 한 핸들은 네이티브 c + +에 대 한 포인터와 비슷합니다. 자세한 내용은 참조 [개체 연산자 (^)에 대 한 핸들](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)합니다.  
  
#### <a name="example"></a>예  
 다음 예제에는 Employee 개체에 대 한 핸들을 삽입 하는 방법을 보여 줍니다는 [cliext::set](../dotnet/set-stl-clr.md)합니다.  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
    ~Employee() { }  
  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee^ empl1419 = gcnew Employee();  
    empl1419->Name = L"Darin Lockert";  
    empl1419->EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee^>^ emplSet = gcnew set<Employee^>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee^ empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl->EmployeeNumber, empl->Name);  
    }  
  
    return 0;  
}  
```  
  
### <a name="reference-types"></a>참조 형식  
 STL/CLR 컨테이너에는 참조 형식 (참조 형식에 대 한 핸들 아님)를 삽입 하는 것도 가능 합니다. 여기서는 중요 한 차이점은 참조 형식의 컨테이너 삭제 되 면 해당 컨테이너 내의 모든 요소에 대해 소멸자가 호출 됩니다. 참조 형식에 대 한 핸들의 컨테이너에서 이러한 요소에 대 한 소멸자가 호출 되지 않습니다.  
  
#### <a name="example"></a>예  
 다음 예제에는 Employee 개체를 삽입 하는 방법을 보여 줍니다는 `cliext::set`합니다.  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
    ~Employee() { }  
  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee empl1419;  
    empl1419.Name = L"Darin Lockert";  
    empl1419.EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee>^ emplSet = gcnew set<Employee>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee^ empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl->EmployeeNumber, empl->Name);  
    }  
  
    return 0;  
}  
```  
  
### <a name="unboxed-value-types"></a>Unboxed 값 형식  
 STL/CLR 컨테이너에 unboxed 값 형식을 삽입할 수도 있습니다. Unboxed 값 형식 값 형식이 되지 않은 *boxed* 참조 형식으로.  
  
 값 형식 요소와 같은 표준 값 형식 중 하나일 수 있습니다는 `int`와 같은 사용자 정의 값 형식 될 수도 있습니다는 `value class`합니다. 자세한 내용은 참조 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### <a name="example"></a>예  
 다음 예제에서는 값 형식 클래스 직원 하 여 첫 번째 예제를 수정 합니다. 이 값 형식이 다음 삽입 한 `cliext::set` 첫 번째 예제에서와 마찬가지로 합니다.  
  
```  
// cliext_container_valid_valuetype.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
value class Employee  
{  
public:  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee empl1419;  
    empl1419.Name = L"Darin Lockert";  
    empl1419.EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee>^ emplSet = gcnew set<Employee>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl.EmployeeNumber, empl.Name);  
    }  
  
    return 0;  
}  
```  
  
 컨테이너, 값 형식에 대 한 핸들을 삽입 하려고 하면 [컴파일러 오류 C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) 생성 됩니다.  
  
### <a name="performance-and-memory-implications"></a>성능 및 메모리에 미치는 영향  
 형식 또는 값 형식으로 컨테이너 요소를 참조 하려면 핸들을 사용할 것인지 결정할 때 여러 가지 요소를 고려해 야 합니다. 값 형식을 사용 하려는 경우 컨테이너에 요소를 삽입 될 때마다 요소의 복사본을 만들 기억 합니다. 작은 개체에 대 한이 문제가 아니어야 하지만 삽입 될 개체가 큰 경우 성능이 저하 될 수 있습니다. 또한, 값 형식을 사용 하는 인지 각 컨테이너 요소의 자체 복사본을 갖기 때문에 여러 컨테이너에 요소가 두 개를 동시에 저장할 수 없습니다.  
  
 참조 형식 대신에 핸들을 사용 하려는 경우 컨테이너에 삽입 되는 요소의 복사본을 만들 필요가 없기 때문에 성능이 증가할 수 있습니다. 또한 달리와 값 형식을 동일한 요소 존재할 수 있습니다 여러 컨테이너에 있습니다. 그러나 핸들을 사용 하는 경우 주의 해야 핸들이 유효한 지 확인 하 고 참조 된 개체는 삭제 되지 않았는지 다른 곳에서 프로그램에 있습니다.  
  
## <a name="ownership-issues-with-containers"></a>컨테이너와 소유권 문제  
 STL/CLR 컨테이너 값 의미 체계에서 작동 합니다. 컨테이너에 요소를 삽입 될 때마다 해당 요소의 복사본 삽입 됩니다. 참조 형식 의미 체계를 확보 하려는 경우에 개체 자체가 아니라 개체에 대 한 핸들을 삽입할 수 있습니다.  
  
 일반 텍스트 전화를 하거나 erase 핸들 개체의 컨테이너의 메서드, 개체 핸들에서 참조 하는 메모리에서 해제 되지 않습니다. 명시적으로 개체를 삭제 하거나, 관리 되는 힙에 저장 된이 개체 개체가 더 이상 사용 되지 않음을 확인 되 면 메모리를 확보 하기 위해 가비지 수집기를 허용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)