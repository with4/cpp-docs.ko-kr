---
title: "break 문 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "break_cpp"
  - "break"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "break 키워드[C++]"
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# break 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`break` 문은 가장 가까운 바깥쪽 루프 또는 표시되는 조건문의 실행을 종료합니다.  제어는 종료된 문 뒤의 문이 있는 경우 전달됩니다.  
  
## 구문  
  
```  
break;  
```  
  
## 설명  
 `break` 문은 [switch](../cpp/switch-statement-cpp.md) 조건문 및 [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) 및 [while](../cpp/while-statement-cpp.md) 루프 문과 함께 사용됩니다.  
  
 `switch` 문에서 `break` 문을 사용하면 프로그램이 `switch` 문 외부에서 다음 문을 실행합니다.  `break` 문 없이, `default` 절을 포함하여, `switch` 문 끝에 `case` 레이블에 일치하는 모든 문을 실행합니다.  
  
 루프에서 `break` 문은 가장 가까운 바깥쪽 `do`, `for` 또는 `while` 문의 실행을 종료합니다.  종료된 문 뒤에 문이 있는 경우 제어가 해당 문으로 전달됩니다.  
  
 중첩된 문 내의 `break` 문은 해당 문을 둘러싼 `do`, `for`, `switch` 또는 `while` 문만을 종료합니다.  `return` 또는 `goto` 문을 사용하여 더 많이 중첩된 구조에서 제어를 전송할 수 있습니다.  
  
## 예제  
 다음 코드에서는 `for` 문에서 `break` 문을 사용하는 방법을 보여 줍니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        cout << i << '\n';  
        if (i == 4)  
            break;  
    }  
  
    // An example of a range-based for loop  
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
  
    for (int i : nums) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
    }  
}  
```  
  
  **각 경우 다음과 같은 결과가 나타납니다.**   
**1**  
**2**  
**3** 다음 코드에서는 `while` 루프 및 `do` 루프에서 `break`를 사용하는 방법을 보여 줍니다.  
  
```cpp  
  
#include <iostream>  
using namespace std;  
  
int main() {  
    int i = 0;  
  
    while (i < 10) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    }  
  
    i = 0;  
    do {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    } while (i < 10);  
}  
```  
  
  **각 경우 다음과 같은 결과가 나타납니다.**  
**0**  
**1**  
**2**  
**3** 다음 코드에서는 switch 문에서 `break`를 사용하는 방법을 보여 줍니다.  각각의 경우를 별도로 처리하려면 모든 경우에 `break`를 사용해야 합니다. `break`를 사용하지 않는 경우 코드 실행은 다음 경우로 이동합니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
enum Suit{ Diamonds, Hearts, Clubs, Spades };  
  
int main() {  
  
    Suit hand;  
    . . .  
    // Assume that some enum value is set for hand  
    // In this example, each case is handled separately  
    switch (hand)  
    {  
    case Diamonds:  
        cout << "got Diamonds \n";  
        break;  
    case Hearts:  
        cout << "got Hearts \n";  
        break;  
    case Clubs:  
        cout << "got Clubs \n";  
        break;  
    case Spades:  
        cout << "got Spades \n";  
        break;  
    default:   
          cout << "didn't get card \n";  
    }  
    // In this example, Diamonds and Hearts are handled one way, and  
    // Clubs, Spades, and the default value are handled another way  
    switch (hand)  
    {  
    case Diamonds:  
    case Hearts:  
        cout << "got a red card \n";  
        break;  
    case Clubs:  
    case Spades:   
    default:  
        cout << "didn't get a red card \n";  
    }  
}  
```  
  
## 참고 항목  
 [점프 문](../cpp/jump-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [continue 문](../cpp/continue-statement-cpp.md)