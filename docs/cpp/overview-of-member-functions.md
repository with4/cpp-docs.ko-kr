---
title: "멤버 함수 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인라인 함수, 멤버 함수를 인라인 함수로 처리"
  - "멤버 함수, 클래스 선언에서의 정의"
  - "비정적 멤버 함수"
  - "this 포인터, 비정적 멤버 함수"
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 멤버 함수 개요
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

멤버 함수는 정적이거나 비정적입니다.  정적 멤버 함수에는 암시적인 **this** 인수가 없으므로 정적 멤버 함수의 동작은 다른 멤버 함수의 동작과 다릅니다.  비정적 멤버 함수에는 **this** 포인터가 있습니다.  정적이든 비정적이든 클래스 선언 안이나 밖에서 멤버 함수를 정의할 수 있습니다.  
  
 멤버 함수가 클래스 선언 안에 정의될 경우 인라인 함수로 처리되며 함수 이름을 클래스 이름으로 정규화할 필요가 없습니다.  클래스 선언 안에 정의된 함수가 이미 인라인 함수로 처리된 경우에도 **inline** 키워드를 사용하여 코드를 문서화할 수 있습니다.  
  
 클래스 선언 안에 함수를 선언하는 예제는 다음과 같습니다.  
  
```  
// overview_of_member_functions1.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit within the declaration  
    //  of class Account.  
    double Deposit( double HowMuch )  
    {  
        balance += HowMuch;  
        return balance;  
    }  
private:  
    double balance;  
};  
  
int main()  
{  
}  
```  
  
 멤버 함수의 정의가 클래스 선언 밖에 있는 경우 **inline**으로 명시적으로 선언되어야 인라인 함수로 처리됩니다.  또한 범위 결정 연산자\(`::`\)를 사용하여 클래스 이름으로 정의 안의 함수 이름을 정규화해야 합니다.  
  
 다음 예제는 `Deposit` 함수가 클래스 선언 밖에 정의된 점을 제외하고 위의 `Account` 클래스 선언과 동일합니다.  
  
```  
// overview_of_member_functions2.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit but do not define it.  
    double Deposit( double HowMuch );  
private:  
    double balance;  
};  
  
inline double Account::Deposit( double HowMuch )  
{  
    balance += HowMuch;  
    return balance;  
}  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  클래스 선언 안에 또는 별도로 멤버 함수를 정의할 수 있지만 클래스가 정의된 후에는 클래스에 멤버 함수를 추가할 수 없습니다.  
  
 멤버 함수가 포함된 클래스는 많은 선언을 포함할 수 있지만 멤버 함수 자체는 프로그램에 정의를 하나만 포함해야 합니다.  정의가 여러 개 있으면 링크 타임에 오류 메시지가 표시됩니다.  클래스에 인라인 함수 정의가 포함된 경우 함수 정의가 동일해야 이 "단일 정의" 규칙을 지킬 수 있습니다.  
  
## 참고 항목  
 [멤버 함수](../misc/member-functions-cpp.md)