---
title: "goto 문 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- goto_cpp
- goto
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3bdad97f36902762f34816a04a4fc0c5c0c16856
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="goto-statement-c"></a>goto 문 (C++)
`goto` 문은 지정된 식별자로 레이블이 지정된 문으로 무조건적으로 컨트롤을 전송합니다.  
  
## <a name="syntax"></a>구문  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>설명  
 `identifier`에 의해 지정된 레이블 문은 현재 함수에 있어야 합니다. 모든 `identifier` 이름은 내부 네임스페이스의 멤버이므로 다른 식별자를 방해하지 않습니다.  
  
 문 레이블은 `goto` 문에 대해서만 유의미하고, 그렇지 않은 경우 문 레이블은 무시됩니다. 레이블을 다시 선언할 수 없습니다.  
  
 가능하다면 최대한 `goto` 문 대신 `break`, `continue` 및 `return` 문을 사용하는 것이 좋은 프로그래밍 스타일입니다. 그러나 `break` 문은 한 수준의 루프만 종료하므로, 많이 중첩된 루프를 종료하려면 `goto` 문을 사용해야 할 수도 있습니다.  
  
 레이블에 대 한 자세한 내용은 및 `goto` 문을 참조 [Labeled 문](../cpp/labeled-statements.md) 및 [goto 문 사용 하 여 레이블을](http://msdn.microsoft.com/en-us/6cd7c31a-9822-4241-8566-f79f51be48fe)합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `i`가 3일 때 `goto`문이 `stop`이라는 레이블이 지정된 지점으로 컨트롤을 전송합니다.  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
```Output  
Outer loop executing. i = 0  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 1  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 2  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 3  
 Inner loop executing. j = 0  
Jumped to stop. i = 3  
```  
  
## <a name="see-also"></a>참고 항목  
 [점프 문](../cpp/jump-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)
