---
title: "참조 형식 함수 인수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 63eb2b4c7415dc463b38346909bd2b6fd902c332
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="reference-type-function-arguments"></a>참조 형식 함수 인수
보통은 큰 개체보다 참조를 함수에 전달하는 것이 더 효율적입니다. 이렇게 하면 개체에 액세스하는 데 사용된 구문을 유지하면서 컴파일러가 개체의 주소를 전달할 수 있습니다. `Date` 구조체를 사용하는 다음 예제를 살펴보십시오.  
  
```  
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
  
 위의 코드는 참조로 전달 되는 구조체의 멤버는 멤버 선택 연산자를 사용 하 여 액세스 하는 보여 줍니다 (**.**) 포인터 멤버 선택 연산자 대신 (**->**).  
  
 포인터 형식의 중요 한 특성 참조 형식으로 전달 된 인수는 포인터가 아닌 형식의 구문을 준수, 하지만 유지:로 선언 되지 않은 수정할 수는 **const**합니다. 이 코드에는 `GDate` 개체를 수정할 의도가 없기 때문에 더 적절한 함수 프로토타입은 다음과 같습니다.  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 이 프로토타입은 `JulianFromGregorian` 함수가 인수를 변경하지 않도록 합니다.  
  
 참조 형식으로 프로토타입 모든 함수에서 표준 변환 되기 때문에 해당 위치에 동일한 형식의 개체를 허용할 수 *typename* 를 *typename*  **&** .  
  
## <a name="see-also"></a>참고 항목  
 [참조](../cpp/references-cpp.md)