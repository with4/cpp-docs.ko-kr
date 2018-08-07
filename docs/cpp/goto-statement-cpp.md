---
title: goto 문 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aae9429754dab8c539d7b94e70db72d33e4f13b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402574"
---
# <a name="goto-statement-c"></a>goto 문 (C++)
합니다 **goto** 문은 지정된 된 식별자로 레이블이 지정 된 문에 무조건 제어를 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>설명  
 `identifier`에 의해 지정된 레이블 문은 현재 함수에 있어야 합니다. 모든 `identifier` 이름은 내부 네임스페이스의 멤버이므로 다른 식별자를 방해하지 않습니다.  
  
 문 레이블은에 의미가 **goto** 문과 그렇지 않은 경우 문 레이블은 무시 됩니다. 레이블을 다시 선언할 수 없습니다.  
  
 더 좋은 프로그래밍 스타일을 사용 하 여는 **나누기**, **계속**, 및 **반환** 문 대신 합니다 **goto** 문을 때마다 가능 합니다. 그러나 때문에 **나누기** 문은 한 수준의 루프에서 종료, 사용 해야 할 수 있습니다를 **goto** 문을 여러 번 중첩 된 루프를 종료 합니다.  
  
 레이블에 대 한 자세한 내용은 하며 **goto** 문을 참조 하십시오 [Labeled 문](../cpp/labeled-statements.md)합니다.  
  
## <a name="example"></a>예  
 이 예는 **goto** 문은 레이블이 지정 된 지점으로 제어 `stop` 때 `i` 3.  
  
```cpp  
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
  
## <a name="see-also"></a>참고자료  
 [점프 문](../cpp/jump-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)