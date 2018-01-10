---
title: "간단한, 표준 레이아웃 및 POD 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
caps.latest.revision: "13"
manager: ghogen
ms.openlocfilehash: b2aa887d4838a9c33e7cfdc360055ca8700d9850
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="trivial-standard-layout-and-pod-types"></a>간단한, 표준 레이아웃 및 POD 형식
용어 *레이아웃* 메모리의 클래스, 구조체 또는 공용 구조체 형식 개체의 멤버 정렬 방법을 가리킵니다. 경우에 따라 레이아웃 언어 사양에 잘 정의 되어 있습니다. 하지만 클래스 또는 구조체에는 가상 기본 클래스, 가상 함수, 서로 다른 액세스 제어를 사용한 멤버 등의 특정 c + + 언어 기능을 포함 되어 있으면, 다음 컴파일러는 자유롭게 레이아웃을 선택할 수 있습니다. 해당 레이아웃 어떤 최적화가 수행 되 고에 따라 다를 수 있습니다 및 대부분의 경우에서 개체 하지도 차지할 수 인접 한 메모리 영역입니다. 예를 들어, 클래스에 가상 함수가, 해당 클래스의 모든 인스턴스 수 단일 가상 함수 테이블을 공유 합니다. 이러한 형식은 물론 매우 유용 하지만 또한 제한이 있습니다. 레이아웃 정의 하지 않으므로 C와 같은 다른 언어로 작성 된 프로그램에 전달할 수 없습니다와 비연속적 될 수 있으므로 이러한 없습니다 안정적으로 복사 빠른 하위 수준 함수를 사용한와 같은 `memcopy` 되거나 네트워크를 통해 serialize 합니다.  
  
 컴파일러 및 c + + 프로그램 및 특정 메모리 레이아웃에 의존 하는 작업에 대 한 지정 된 형식의 적합성에 대 한 이유를 metaprograms를 사용 하려면 C + + 14 도입 간단한 클래스 및 구조체의 세 가지 범주: *trivial*, *표준 레이아웃*, 및 *POD* 또는 일반 이전 데이터입니다. 표준 라이브러리의 함수 템플릿 `is_trivial<T>`, `is_standard_layout<T>` 및 `is_pod<T>` 없음과 같은 형식이 지정된 된 범주에 속하는지 여부를 결정 하는 합니다.  
  
## <a name="trivial-types"></a>Trivial 형식  
 경우 클래스 또는 구조체에서 c + + 컴파일러에서 제공 했거나이 trivial 형식인 다음 특수 멤버 함수를 명시적으로 기본 설정 합니다. 인접 한 메모리 영역을 차지합니다. 서로 다른 액세스 지정자와 함께 멤버를 가질 수 있습니다. 컴파일러는 c + +에서는 자유롭게이 상황에서 멤버를 정렬 하는 방법을 선택할 수 있습니다. 따라서 memcopy 이러한 개체를 수 있지만 C 프로그램에서 안정적으로 사용할 수 없습니다. Trivial 형식 T char 또는 부호 없는 문자 배열에 복사 하 고 안전 하 게 T 변수로 다시 복사 수 있습니다. 맞춤 요구 사항으로 인해를 형식 멤버 간의 패딩 바이트 있을 수 있습니다.  
  
 Trivial 형식에 trivial 기본 생성자, trivial 복사 생성자, trivial 복사 할당 연산자 및 trivial 소멸자 있어야 합니다. 각각의 경우에서 *trivial* 고가 있는 클래스에 속해 있는 않은 사용자가 제공한 생성자/연산자/소멸자  
  
-   가상 함수 또는 가상 기본 클래스 없음  
  
-   해당 특수 생성자/연산자/소멸자가 있는 기본 클래스 없음  
  
-   해당 특수 생성자/연산자/소멸자가 있는 클래스 형식의 데이터 멤버 없음  
  
 다음 예제에서는 trivial 형식을 보여 줍니다. Trivial2의 존재에에서는 `Trivial2(int a, int b)` 생성자를 사용 하려면 기본 생성자를 제공 합니다. Trivial으로 처리 유형에 대 한 생성자를 명시적으로 기본값으로 해야 합니다.  
  
```cpp  
struct Trivial  
{   
    int i;  
private:  
    int j;    
};  
  
struct Trivial2  
{   
    int i;  
    Trivial2(int a, int b) : i(a), j(b) {}  
    Trivial2() = default;   
private:  
    int j;  // Different access control  
};  
  
```  
  
## <a name="standard-layout-types"></a>표준 레이아웃 유형  
 클래스 또는 구조체는 가상 함수는 C 언어에서 제공 되지 않는 등의 특정 c + + 언어 기능 하 고 모든 구성원이 동일한 액세스 제어를 표준 레이아웃 형식입니다. Memcopy 수 및 레이아웃 C 프로그램에서 사용할 수 있는지를 충분히 정의 됩니다. 표준 레이아웃 형식을 사용자 정의 특수 멤버 함수를 사용할 수도 있습니다. 또한 표준 레이아웃 형식은 이러한 특징을 가집니다.  
  
-   가상 함수 또는 가상 기본 클래스 없음  
  
-   동일한 액세스 권한이 모든 비정적 데이터 멤버  
  
-   클래스 형식의 모든 비정적 멤버는 표준 레이아웃  
  
-   모든 기본 클래스는 표준 레이아웃  
  
-   첫 번째 비정적 데이터 멤버와 동일한 형식의 기본 클래스 없음에 있습니다.  
  
-   다음이 조건 중 하나를 충족합니다.  
  
    -   비정적 데이터 멤버가 포함 된 가장 많이 파생 된 클래스 및 둘 이상의 기본 클래스의 비정적 데이터 멤버 또는  
  
    -   이 비정적 데이터 멤버와 기본 클래스 없음  
  
 다음 코드에서는 표준 레이아웃 형식의 한 가지 예를 보여 줍니다.  
  
```cpp  
struct SL   
{     
   // All members have same access:  
   int i;  
    int j;  
    SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK  
};  
  
```  
  
 마지막 두 가지 요구 사항이 코드와 함께 더 잘 설명 아마도 수 있습니다. 다음 예제에서는 경우에 자료는 표준 레이아웃 `Derived` 때문에 표준 레이아웃 않습니다 it (가장 많이 파생 된 클래스) 및 `Base` 비정적 데이터 멤버가:  
  
```cpp  
struct Base  
{  
    int i;  
    int j;  
};  
  
// std::is_standard_layout<<Derived> == false!  
struct Derived : public Base  
{  
    int x;  
    int y;  
};  
  
```  
  
 이 예에서 `Derived` 표준 레이아웃은 때문에 `Base` 비정적 데이터 멤버가 없습니다.  
  
```cpp  
struct Base  
{  
    void Foo() {}  
};  
  
// std::is_standard_layout<<Derived> == true  
struct Derived : public Base  
{  
    int x;  
    int y;  
};  
```  
  
 파생 된 수도 표준 레이아웃 경우 `Base` 데이터 멤버에 및 `Derived` 멤버 함수만 했습니다.  
  
## <a name="pod-types"></a>POD 형식  
 클래스 또는 구조체 이면 간단한 문제가 아니며 표준 레이아웃 POD (Plain Old Data) 형식입니다. POD 형식의 메모리 레이아웃 이며 연속 따라서 각 구성원에 게는 더 높은 주소 보다 바이트에 대 한 바이트 복사할 수 없도록 그 이전의 선언 된 멤버와 이진 I/O 이러한 형식에서 수행할 수 있습니다.  Int와 같은 스칼라 형식 POD 형식 됩니다. 클래스는 POD 형식 비정적 데이터 멤버로 POD 유형만 가질 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 간단한, 표준 레이아웃 간의 개념적인 차이 및 POD 형식:  
  
```cpp  
#include <type_traits>  
#include <iostream>  
  
using namespace std;  
  
struct B  
{  
protected:  
    virtual void Foo() {}  
};  
  
// Neither trivial nor standard-layout  
struct A : B  
{   
    int a;  
    int b;  
    void Foo() override {} // Virtual function  
};  
  
// Trivial but not standard-layout  
struct C   
{   
    int a;  
private:  
    int b;  // Different access control  
};  
  
// Standard-layout but not trivial  
struct D   
{   
    int a;  
    int b;  
    D() {} //User-defined constructor  
};  
  
struct POD   
{  
    int a;  
    int b;  
};  
  
int main()  
{  
 cout << boolalpha;  
    cout << "A is trivial is " << is_trivial<A>() << endl; // false  
    cout << "A is standard-layout is " << is_standard_layout<A>() << endl;  // false  
  
    cout << "C is trivial is " << is_trivial<C>() << endl; // true  
    cout << "C is standard-layout is " << is_standard_layout<C>() << endl;  // false  
  
    cout << "D is trivial is " << is_trivial<D>() << endl;  // false  
    cout << "D is standard-layout is " << is_standard_layout<D>() << endl; // true  
  
    cout << "POD is trivial is " << is_trivial<POD>() << endl; // true  
    cout << "POD is standard-layout is " << is_standard_layout<POD>() << endl; // true  
  
return 0;  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [기본 개념](../cpp/basic-concepts-cpp.md)