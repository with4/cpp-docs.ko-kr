---
title: 값 형식 (최신 c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e49c97bca86b8d2debde2f5b132f7dde16998e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423420"
---
# <a name="value-types-modern-c"></a>값 형식(최신 C++)
C + + 클래스는 기본 값 형식으로 됩니다. 이 항목에서는 값 형식 및 용도 관련 된 문제 소개 개요를 제공 합니다.  
  
## <a name="value-vs-reference-types"></a>참조 형식 및 값  
 듯이 c + + 클래스 기본 값 형식으로 되어 있습니다. 개체 지향 프로그래밍을 지 원하는 다형성 동작을 사용할 수 있는 참조 형식으로 지정할 수 있습니다. 반면 다형 목적에 대 한 기본 클래스 및 가상 함수에 대 한 참조 형식을 값 형식은 메모리 및 레이아웃 컨트롤의 관점에서 표시 경우가 됩니다. 기본적으로 값 형식을 복사할 수 있습니다,으로, 항상 복사 생성자와 복사 할당 연산자입니다. 참조 형식에 대 한 클래스를 설정 복사할 수 없는 (복사 생성자와 복사 할당 연산자 사용 안 함)가 의도 한 다형성을 지 원하는 가상 소멸자를 사용 합니다. 값 형식은 복사 될 때 항상 사용 하면 개별적으로 수정할 수 있는 독립적인 값 두 개 있는 내용에 대 한도 있습니다. 참조 유형은 id-입니까 어떤 종류의 개체에 대 한? 이러한 이유로 "은 형식을 참조 하 고"는 "다형 형식" 라고도 합니다.  
  
 참조 형식의 형식 (기본 클래스, 가상 함수)를 원하는 경우 명시적으로 해제 해야 복사에 표시 된 대로 `MyRefType` 다음 코드에서는 클래스입니다.  
  
```cpp  
// cl /EHsc /nologo /W4  
  
class MyRefType {  
private:  
    MyRefType & operator=(const MyRefType &);  
    MyRefType(const MyRefType &);  
public:  
    MyRefType () {}  
};  
  
int main()  
{  
    MyRefType Data1, Data2;  
    // ...  
    Data1 = Data2;  
}  
```  
  
 위의 코드 컴파일 다음과 같은 오류가 발생 합니다.  
  
```Output  
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'  
        meow.cpp(5) : see declaration of 'MyRefType::operator ='  
        meow.cpp(3) : see declaration of 'MyRefType'  
  
```  
  
## <a name="value-types-and-move-efficiency"></a>값 형식 및 효율성을 이동  
 새 복사 최적화로 인해 복사 할당 오버 헤드를 피할 수 있습니다. 예를 들어 문자열의 벡터가 중간에 문자열을 삽입 됩니다 복사 재할당 오버 헤드 없음만 이동-자체 벡터의 grow 발생 하는 경우에 합니다. 예를 들어 두 개의 매우 큰 개체에 추가 작업을 수행 합니다. 다른 작업에도 적용 됩니다. 이러한 값 작업 최적화 어떻게 사용 합니까? 일부 c + + 컴파일러에서는 컴파일러 설정이를 암시적으로 컴파일러에서 복사 생성자를 자동으로 생성 수와 아주 유사 합니다. 그러나, Visual c + +에서 클래스 "에 참여 하는" 클래스 정의에 선언 하 여 할당 및 생성자를 이동 해야 합니다. 이중 앰퍼샌드를 사용 하 여이 작업 수행 됩니다 (& &) 함수 선언 및 정의 이동 생성자 및 이동 할당 방법의 적절 한 멤버에 대 한 rvalue 참조입니다.  또한 "는 주 도용" 하 여 원본 개체에서 올바른 코드를 삽입 해야 합니다.  
  
 활성화 이동 해야 하는 경우 어떻게 결정 합니까? 복사 필요 사용 하도록 설정 하는 생성 이미 알고 있는 경우 전체 복사본을 보다 저렴 수 있으면 활성화 이동는 것이 싶을입니다. 그러나 지원 이동 필요를 알고 있는 경우이 반드시 의미 복사본을 사용 하도록 설정 합니다. 후자의 경우가는 "이동 전용 형식은" 이라고 합니다. 표준 라이브러리에 이미 있는 예로 `unique_ptr`합니다. 이전 보조 노트도 `auto_ptr` 는 더 이상으로 대체 되었으며 `unique_ptr` c + +의 이전 버전에 이동 의미 체계 지원 부족으로 인해 정확 하 게 합니다.  
  
 이동 의미 체계를 사용 하 여 반환 값 또는 중간에 삽입을 수 있습니다. 이동은 복사본의 최적화 됩니다. 해결 방법으로 힙 할당에 대 한 필요가 않습니다. 다음 의사 코드를 살펴보겠습니다.  
  
```cpp  
#include <set>  
#include <vector>  
#include <string>  
using namespace std;  
  
//...  
set<widget> LoadHugeData() {  
    set<widget> ret;  
    // ... load data from disk and populate ret  
    return ret;  
}  
//...  
widgets = LoadHugeData();   // efficient, no deep copy  
  
vector<string> v = IfIHadAMillionStrings();  
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle  
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)  
//...  
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );  
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);  
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );  
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);  
//...  
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies  
```  
  
### <a name="enabling-move-for-appropriate-value-types"></a>적절 한 값 형식에 대해 move를 사용 하도록 설정  
 이동 전체 복사본을 보다 저렴 될 수 있는 값 형식의 클래스에 대 한 이동 생성을 사용 하도록 설정 하 고 효율성에 대 한 할당을 이동 합니다. 다음 의사 코드를 살펴보겠습니다.  
  
```cpp  
#include <memory>  
#include <stdexcept>  
using namespace std;  
// ...  
class my_class {  
    unique_ptr<BigHugeData> data;  
public:  
    my_class( my_class&& other )   // move construction  
        : data( move( other.data ) ) { }  
    my_class& operator=( my_class&& other )   // move assignment  
    { data = move( other.data ); return *this; }  
    // ...  
    void method() {   // check (if appropriate)  
        if( !data )   
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");  
    }  
};  
  
```  
  
 복사 생성/할당을 사용 하도록 설정 하면 전체 복사본을 보다 저렴 수 있는 경우 이동 생성/할당을 통해 수도 있습니다.  
  
 일부 *값이 아닌* 유형은 이동 전용 같은 경우 소유권을 이전만 리소스를 복제할 수 없습니다. 예를 들어, `unique_ptr` 같은 형식입니다.  
  
## <a name="section"></a>단원  
 콘텐츠  
  
## <a name="see-also"></a>참고 항목  
 [C + + 형식 시스템](../cpp/cpp-type-system-modern-cpp.md)   
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)