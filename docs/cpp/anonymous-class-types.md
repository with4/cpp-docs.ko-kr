---
title: "익명 클래스 형식 | Microsoft Docs"
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
  - "익명 클래스 형식"
  - "클래스 형식, 무명"
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 익명 클래스 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스는 익명일 수 있으므로 식별자 없이 선언할 수 있습니다.  다음과 같이 클래스 이름을 `typedef` 이름으로 바꿀 때 유용합니다.  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
> [!NOTE]
>  이전 예제와 같이 익명 클래스를 사용하면 기존의 C 코드와 호환성을 유지하는 데 도움이 됩니다.  일부 C 코드에서는 익명 구조체와 함께 `typedef`를 사용하는 것이 일반적입니다.  
  
 다음과 같이 클래스 멤버를 참조하여 별도의 클래스에 포함되지 않은 것처럼 나타내려는 경우에도 익명 클래스가 유용합니다.  
  
```  
struct PTValue  
{  
    POINT ptLoc;  
    union  
    {  
        int  iValue;  
        long lValue;  
    };  
};  
  
PTValue ptv;  
```  
  
 앞의 코드에서 다음과 같이 개체 멤버 선택 연산자\(`iValue`.\)를 사용하여 **에 액세스할 수 있습니다.**  
  
```  
int i = ptv.iValue;  
```  
  
 특정 제한이 익명 클래스에 적용됩니다.  익명 공용 구조체에 대한 자세한 내용은 [공용 구조체](../cpp/unions.md)를 참조하세요. 익명 클래스:  
  
-   생성자나 소멸자를 가질 수 없습니다.  
  
-   타원을 사용하여 형식 검사를 통과하지 않으면 함수에 인수로 전달할 수 없습니다.  
  
-   함수에서 반환 값으로 반환될 수 없습니다.  
  
## 익명 구조체  
  
### Microsoft 전용  
 Microsoft C 확장을 사용하면 이름을 지정하지 않고 다른 구조체 내에서 구조체 변수를 선언할 수 있습니다.  이러한 중첩된 구조체를 익명 구조체라고 합니다.  C\+\+에서는 익명 구조체를 허용하지 않습니다.  
  
 포함하는 구조체의 멤버인 것처럼 익명 구조체의 멤버에 액세스할 수 있습니다.  
  
```  
// anonymous_structures.c  
#include <stdio.h>  
  
struct phone  
{  
    int  areacode;  
    long number;  
};  
  
struct person  
{  
    char   name[30];  
    char   gender;  
    int    age;  
    int    weight;  
    struct phone;    // Anonymous structure; no name needed  
} Jim;  
  
int main()  
{  
    Jim.number = 1234567;  
    printf_s("%d\n", Jim.number);     
}  
//Output: 1234567  
```  
  
### Microsoft 전용 종료  
  
## 참고 항목  
 [\(NOTINBUILD\) Defining Class Types](http://msdn.microsoft.com/ko-kr/e8c65425-0f3a-4dca-afc2-418c3b1e57da)