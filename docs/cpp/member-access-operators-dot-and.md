---
title: 멤버 액세스 연산자:. 및-&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91ec7e11272e0a7286d77e3fc96b7437007a0f8d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408788"
---
# <a name="member-access-operators--and--gt"></a>멤버 액세스 연산자:. and -&gt;
## <a name="syntax"></a>구문  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>설명  
 멤버 액세스 연산자 **합니다.** 및 **->** 구조체, 공용 구조체 및 클래스의 멤버를 참조 하는 데 사용 됩니다. 멤버 액세스 식에는 선택한 멤버의 값과 형식이 있습니다.  
  
 다음 두 가지 형태의 멤버 액세스 식이 있습니다.  
  
1.  첫 번째 형태에서 *후 위 식* 구조체, 클래스 또는 공용 구조체 유형이 면 값을 나타내며 및 *이름* 지정된 구조체, 공용 구조체 또는 클래스의 멤버 이름을 지정 합니다. 작업의 값을 사용 하면의 임을 *이름을* 경우 l-value 및 *후 위 식* l-value는 합니다.  
  
2.  두 번째 형태에서 *후 위 식* 구조체, 공용 구조체 또는 클래스에 대 한 포인터를 나타냅니다와 *이름* 지정된 구조체, 공용 구조체 또는 클래스의 멤버 이름을 지정 합니다. 값이 *이름을* 이며 l-value입니다. 합니다 **->** 연산자는 포인터를 역참조 합니다. 따라서 식 *e***->**`member` 및 **(\****e***)** 합니다.`member` (여기서 *e* 포인터 나타냅니다) 동일한 결과 생성 (경우는 제외 연산자 **->** 또는 **\*** 는 오버 로드).  
  
## <a name="example"></a>예  
 다음 예제에서는 두 가지 형태의 멤버 액세스 연산자를 보여 줍니다.  
  
```cpp 
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
```Output  
2/1/1900  
2/1/2000  
```  
  
## <a name="see-also"></a>참고자료  
 [후 위 식](../cpp/postfix-expressions.md)   
 [C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)   
 [구조체 및 공용 구조체 구성원](../c-language/structure-and-union-members.md)