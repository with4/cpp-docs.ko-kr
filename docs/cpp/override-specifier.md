---
title: 재정의 지정자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c95a67df03f62279b7b9c46ef41b6cafe7ff3df1
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408153"
---
# <a name="override-specifier"></a>override 지정자
사용할 수는 **재정의** 키워드를 기본 클래스의 가상 함수를 재정의 하는 함수 멤버를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
function-declaration override;  
```  
  
## <a name="remarks"></a>설명  
 **재정의** 상황에 맞는 특별 한 경우에만 의미가 이며 멤버 함수 선언 뒤에 사용할 수행 되며이 고, 그렇지 않습니다 예약된 된 키워드입니다.  
  
## <a name="example"></a>예  
 사용 하 여 **재정의** 코드에서 부주의 한 상속 동작을 방지할 수 있도록 합니다. 다음 예제에서는 사용 하지 않고, 위치를 보여 줍니다. **재정의**, 파생된 클래스의 멤버 함수 동작이 의도 되지 않을 수 있습니다. 컴파일러는 이 코드의 오류를 내보내지 않습니다.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA(); // ok, works as intended  
  
    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not  
                          // override BaseClass::funcB() const and it is a new member function  
  
    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different  
                                      // parameter type than BaseClass::funcC(int), so  
                                      // DerivedClass::funcC(double) is a new member function  
};  
```  
  
 사용 하는 경우 **재정의**, 컴파일러는 자동으로 새 멤버 함수를 만드는 대신 오류를 생성 합니다.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA() override; // ok  
  
    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not   
                                   // override BaseClass::funcB() const  
  
    virtual void funcC( double = 0.0 ) override; // compiler error:   
                                                 // DerivedClass::funcC(double) does not   
                                                 // override BaseClass::funcC(int)  
  
    void funcD() override; // compiler error: DerivedClass::funcD() does not   
                           // override the non-virtual BaseClass::funcD()  
};  
```  
  
 함수를 재정의할 수 없습니다 및 클래스를 상속할 수 없습니다 지정 하려면 사용 합니다 [최종](../cpp/final-specifier.md) 키워드입니다.  
  
## <a name="see-also"></a>참고자료  
 [final 지정자](../cpp/final-specifier.md)   
 [키워드](../cpp/keywords-cpp.md)   