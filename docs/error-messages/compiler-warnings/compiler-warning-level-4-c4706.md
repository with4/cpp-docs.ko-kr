---
title: "컴파일러 경고 (수준 4) C4706 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4706"
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 4) C4706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

조건식 내에 할당이 있습니다.  
  
 조건식의 테스트 값이 할당의 결과입니다.  
  
 테스트 식을 포함하여 적합하게 다른 식에 사용할 수 있는 값이 할당의 왼쪽에 있습니다.  
  
 다음 샘플에서는 C4706 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 테스트 조건에 괄호를 두 개 사용해도 경고가 발생합니다.  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 할당이 아니라 관계를 테스트하는 게 목적이라면 `==` 연산자를 사용하십시오.  예를 들어, 다음 줄에서는 a와 b가 같은지 여부를 테스트합니다.  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 테스트 값을 할당의 결과로 만들려면 할당이 0 또는 null이 아니어야 합니다.  예를 들어, 다음 코드에서는 이 경고가 발생하지 않습니다.  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```