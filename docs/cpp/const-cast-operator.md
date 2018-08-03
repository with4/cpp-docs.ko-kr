---
title: const_cast 연산자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ba0312b255b2957c815bb5f26c97a668d4f7b6d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403026"
---
# <a name="constcast-operator"></a>const_cast 연산자
제거를 **상수**, **volatile**, 및 **__unaligned** 클래스에서 특성.  
  
## <a name="syntax"></a>구문  
  
```  
const_cast <type-id> (expression)  
```  
  
## <a name="remarks"></a>설명  
 임의의 개체 형식에 대 한 포인터 또는 데이터 멤버에 대 한 포인터를 명시적으로 변환할 수는 제외 하 고 동일한 형식에는 **const**를 **volatile**, 및 **__unaligned** 한정자입니다. 포인터 및 참조의 경우 결과는 원래 개체를 참조합니다. 데이터 멤버에 대한 포인터의 경우 결과는 데이터 멤버에 대한 원래(캐스팅 해제) 포인터와 동일한 멤버를 참조합니다. 참조 개체의 형식에 따라 결과 포인터, 참조 또는 데이터 멤버에 대한 포인터를 통한 쓰기 작업으로 인해 정의되지 않은 동작이 발생할 수 있습니다.  
  
 사용할 수 없습니다는 **const_cast** 연산자를 직접 상수 변수의 상수 상태를 재정의 합니다.  
  
 합니다 **const_cast** 연산자 대상 형식의 null 포인터 값으로 null 포인터 값을 변환 합니다.  
  
## <a name="example"></a>예  
  
```cpp 
// expre_const_cast_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CCTest {  
public:  
   void setNumber( int );  
   void printNumber() const;  
private:  
   int number;  
};  
  
void CCTest::setNumber( int num ) { number = num; }  
  
void CCTest::printNumber() const {  
   cout << "\nBefore: " << number;  
   const_cast< CCTest * >( this )->number--;  
   cout << "\nAfter: " << number;  
}  
  
int main() {  
   CCTest X;  
   X.setNumber( 8 );  
   X.printNumber();  
}  
```  
  
 포함 된 줄에는 **const_cast**의 데이터 형식이 합니다 **이** 포인터가 `const CCTest *`. **const_cast** 연산자의 데이터 형식을 변경 합니다 **이** 에 대 한 포인터 `CCTest *`, 멤버 허용 `number` 수정할 합니다. 캐스팅은 그것이 표시되는 문의 나머지 부분에서만 지속됩니다.  
  
## <a name="see-also"></a>참고자료  
 [캐스팅 연산자](../cpp/casting-operators.md)   
 [키워드](../cpp/keywords-cpp.md)