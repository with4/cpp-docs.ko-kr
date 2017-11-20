---
title: "Lvalue 참조 선언 자: &amp; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '&'
dev_langs: C++
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e8a5783a89bc0a9d3bfd8ea9ff0318b894763e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue 참조 선언 자:&amp;
개체의 주소를 보유하지만 구문상 개체처럼 동작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
type-id & cast-expression  
```  
  
## <a name="remarks"></a>설명  
 lvalue 참조를 개체의 또 다른 이름으로 간주할 수 있습니다. lvalue 참조 선언은 참조 선언자가 뒤에 나오는 선택적 지정자 목록으로 구성됩니다. 참조는 초기화되어야 하고 변경될 수 없습니다.  
  
 주소가 지정된 포인터 형식으로 변환될 수 있는 개체는 유사한 참조 형식으로도 변환될 수 있습니다. 예를 들어 주소가 `char *` 형식으로 변환될 수 있는 개체는 `char &` 형식으로도 변환될 수 있습니다.  
  
 사용 하 여 참조 선언을 혼동 하지 마십시오는 [address-of 연산자](../cpp/address-of-operator-amp.md)합니다. 경우는 `&` *식별자* 와 같은 형식으로 앞 `int` 또는 `char`, *식별자* 형식에 대 한 참조로 선언 됩니다. 때 `&` *식별자* 앞에 나오지 않는 사용법은 address-of 연산자의 형식으로.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Person` 개체 및 해당 개체에 대한 참조를 선언하여 참조 선언자를 보여 줍니다. `rFriend`가 `myFriend`에 대한 참조이기 때문에 변수 중 하나를 업데이트하면 동일한 개체가 변경됩니다.  
  
```  
// reference_declarator.cpp  
// compile with: /EHsc  
// Demonstrates the reference declarator.  
#include <iostream>  
using namespace std;  
  
struct Person  
{  
    char* Name;  
    short Age;  
};  
  
int main()  
{  
   // Declare a Person object.  
   Person myFriend;  
  
   // Declare a reference to the Person object.  
   Person& rFriend = myFriend;  
  
   // Set the fields of the Person object.  
   // Updating either variable changes the same object.  
   myFriend.Name = "Bill";  
   rFriend.Age = 40;  
  
   // Print the fields of the Person object to the console.  
   cout << rFriend.Name << " is " << myFriend.Age << endl;  
}  
```  
  
```Output  
Bill is 40  
```  
  
## <a name="see-also"></a>참고 항목  
 [참조](../cpp/references-cpp.md)   
 [참조 형식 함수 인수](../cpp/reference-type-function-arguments.md)   
 [참조 형식 함수 반환 값](../cpp/reference-type-function-returns.md)   
 [포인터에 대한 참조](../cpp/references-to-pointers.md)