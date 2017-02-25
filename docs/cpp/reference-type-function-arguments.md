---
title: "참조 형식 함수 인수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인수[C++], 함수"
  - "함수 인수, 참조 형식"
  - "함수 매개 변수, 참조 형식"
  - "함수[C++], 매개 변수"
  - "매개 변수 전달, 참조 형식 인수"
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 참조 형식 함수 인수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

보통은 큰 개체보다 참조를 함수에 전달하는 것이 더 효율적입니다.  이렇게 하면 개체에 액세스하는 데 사용된 구문을 유지하면서 컴파일러가 개체의 주소를 전달할 수 있습니다.  `Date` 구조체를 사용하는 다음 예제를 살펴보십시오.  
  
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
  
 앞의 코드는 포인터 멤버 선택 연산자\(**–\>**\) 대신에 멤버 선택 연산자\(**.**\)를 사용하여 참조에 의해 전달되는 구조체의 멤버에 액세스하는 방법을 보여 줍니다.  
  
 참조 형식으로 전달된 인수는 포인터가 아닌 형식의 구문을 준수하지만 **const**에서 정의되지 않은 경우 수정할 수 있다는 포인터 형식의 중요한 한 가지 특성을 유지합니다.  이 코드에는 `GDate` 개체를 수정할 의도가 없기 때문에 더 적절한 함수 프로토타입은 다음과 같습니다.  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 이 프로토타입은 `JulianFromGregorian` 함수가 인수를 변경하지 않도록 합니다.  
  
 참조 형식으로 프로토타입된 모든 함수는 *typename*에서 *typename***&**으로의 표준 변환이 있기 때문에 해당 위치에서 같은 형식의 개체를 받을 수 있습니다.  
  
## 참고 항목  
 [참조](../cpp/references-cpp.md)