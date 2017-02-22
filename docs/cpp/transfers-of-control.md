---
title: "컨트롤 전송 | Microsoft Docs"
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
  - "제어 흐름, 분기"
  - "제어 흐름, 제어 전달"
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 컨트롤 전송
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`goto` 문을 사용하거나  **문에서 `switch`case** 레이블을 사용하여 분기가 이니셜라이저를 지나는 프로그램을 지정할 수 있습니다.  이 같은 코드는 이니셜라이저를 포함한 선언이 점프 명령문이 있는 블록이 둘러싼 블록에 없는 경우 올바르지 않습니다.  
  
 다음 예제에서는 `total`, `ch` 및 `i` 개체를 선언하고 초기화하는 루프를 보여 줍니다.  또한 이니셜라이저를 지나 컨트롤을 전송하는 잘못된 `goto` 문이 있습니다.  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 위의 예제에서 `goto` 문은 `i`의 초기화를 지나 컨트롤을 전송합니다.  단, `i`가 선언되었지만 초기화되지 않은 경우 전송은 유효합니다.  
  
 `total` 문의 `ch`statement 역할을 하는 블록 안에서 선언된 개체  *및 `while`는 해당 블록이 `break` 문을 사용하여 종료되는 경우 삭제됩니다.*  
  
## 참고 항목  
 [\(NOTINBUILD\) Declaration of Automatic Objects](http://msdn.microsoft.com/ko-kr/81f941e9-c1b1-4d1c-a28d-70b6ee9765db)