---
title: 컨트롤 전송 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e773a0188eb3450ab1a13a24fc556fa8e8c4f874
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464271"
---
# <a name="transfers-of-control"></a>컨트롤 전송
사용할 수 있습니다는 **goto** 문 또는 **사례** 레이블을 **전환** 분기가 이니셜라이저를 지나는 프로그램을 지정 하는 문. 이 같은 코드는 이니셜라이저를 포함한 선언이 점프 명령문이 있는 블록이 둘러싼 블록에 없는 경우 올바르지 않습니다.  
  
 다음 예제에서는 `total`, `ch` 및 `i` 개체를 선언하고 초기화하는 루프를 보여 줍니다. 이기도 잘못 된 **goto** 이니셜라이저를 지나는 제어를 전송 하는 문입니다.  
  
```cpp 
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
  
 앞의 예제에는 **goto** 문은의 초기화를 지 나 컨트롤을 전송할 `i`합니다. 단, `i`가 선언되었지만 초기화되지 않은 경우 전송은 유효합니다.  
  
 개체 `total` 및 `ch`역할을 하는 블록에서 선언 된를 *문을* 의 **하는 동안** 문을 사용 하 여 해당 블록이 종료 될 때 제거 되는  **나누기** 문입니다.  