---
title: 참조 형식 함수 인수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad8fc85a37aec80d09ed6df9280a78de0540f01
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409058"
---
# <a name="reference-type-function-arguments"></a>참조 형식 함수 인수
보통은 큰 개체보다 참조를 함수에 전달하는 것이 더 효율적입니다. 이렇게 하면 개체에 액세스하는 데 사용된 구문을 유지하면서 컴파일러가 개체의 주소를 전달할 수 있습니다. `Date` 구조체를 사용하는 다음 예제를 살펴보십시오.  
  
```cpp 
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 위의 코드는 참조로 전달 된 구조체의 멤버는 멤버 선택 연산자를 사용 하 여 액세스를 보여 줍니다 (**합니다.**) 대신 포인터 멤버 선택 연산자 (**->**).  
  
 포인터 형식의 중요 한 특징 중 하나를 유지 하 고 참조 형식으로 전달 된 인수는 포인터가 아닌 형식의 구문을 준수, 있지만: 이들은로 선언 되지 않은 수정 가능한 **const**합니다. 이 코드에는 `GDate` 개체를 수정할 의도가 없기 때문에 더 적절한 함수 프로토타입은 다음과 같습니다.  
  
```cpp 
long JulianFromGregorian( const Date& GDate );  
```  
  
 이 프로토타입은 `JulianFromGregorian` 함수가 인수를 변경하지 않도록 합니다.  
  
 표준 변환이 있기 때문에 모든 함수는 참조 형식으로 프로토타입 해당 위치에서 동일한 형식의 개체를 받을 수 있습니다 *typename* 에 * typename ***&** 합니다.  
  
## <a name="see-also"></a>참고자료  
 [참조](../cpp/references-cpp.md)