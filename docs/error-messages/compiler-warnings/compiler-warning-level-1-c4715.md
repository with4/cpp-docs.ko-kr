---
title: "컴파일러 경고 (수준 1) C4715 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4715
dev_langs: C++
helpviewer_keywords: C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b060585cd3ba6b51c9c91d42e5f3fecaf74ae1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4715"></a>컴파일러 경고(수준 1) C4715
'function': 모든 제어 경로 값을 반환  
  
 지정된 된 함수 값을 반환 하지 않을 수 있습니다.  
  
## <a name="example"></a>예  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 이 경고를 방지 하려면 모든 경로 함수에 반환 값이 할당 되도록 코드를 수정 합니다.  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 코드에 반환 하지 않습니다. 다음 예제와 같이 하는 함수에 대 한 호출을 포함할 수 있음을 것 같습니다.  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 이 코드는 또한는 경고를 생성 모르기 때문에 컴파일러는 `fatal` 반환 하지 않습니다. 이 코드는 오류 메시지를 생성 하지 않도록 하려면 선언 `fatal` 를 사용 하 여 [__declspec (noreturn)](../../cpp/noreturn.md)합니다.