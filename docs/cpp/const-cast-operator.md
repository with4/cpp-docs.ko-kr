---
title: "const_cast 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: 7
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
ms.openlocfilehash: 8f72367cb4970b2ce0121efc43b79691155808df
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="constcast-operator"></a>const_cast 연산자
제거는 **const**, `volatile`, 및 **__unaligned** 클래스에서 특성입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## <a name="remarks"></a>설명  
 모든 개체 형식에 대 한 포인터 또는 데이터 멤버에 대 한 포인터를 명시적으로 변환할 수 있는 제외 하 고 동일한 형식으로는 **const**, `volatile`, 및 **__unaligned** 한정자입니다. 포인터 및 참조의 경우 결과는 원래 개체를 참조합니다. 데이터 멤버에 대한 포인터의 경우 결과는 데이터 멤버에 대한 원래(캐스팅 해제) 포인터와 동일한 멤버를 참조합니다. 참조 개체의 형식에 따라 결과 포인터, 참조 또는 데이터 멤버에 대한 포인터를 통한 쓰기 작업으로 인해 정의되지 않은 동작이 발생할 수 있습니다.  
  
 `const_cast` 연산자를 사용하여 상수 변수의 상수 상태를 직접 재정의할 수 없습니다.  
  
 `const_cast` 연산자는 null 포인터 값을 대상 형식의 null 포인터 값으로 변환합니다.  
  
## <a name="example"></a>예제  
  
```  
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
  
 `const_cast`를 포함하는 줄에서 `this` 포인터의 데이터 형식은 `const CCTest *`입니다. `const_cast` 연산자는 `this` 포인터의 데이터 형식을 `CCTest *`로 변경하므로 `number` 멤버가 수정될 수 있습니다. 캐스팅은 그것이 표시되는 문의 나머지 부분에서만 지속됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [캐스팅 연산자](../cpp/casting-operators.md)   
 [키워드](../cpp/keywords-cpp.md)
