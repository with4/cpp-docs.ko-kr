---
title: "컴파일러 오류 C2707 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2707
dev_langs:
- C++
helpviewer_keywords:
- C2707
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 877ca1b0592625823e262f77f7f2adcfc5c04e3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2707"></a>컴파일러 오류 C2707
'identifier': 내장 함수에 대 한 잘못 된 컨텍스트  
  
 구조적된 예외 처리 내장 함수는 특정 컨텍스트에서 유효 하지 않습니다.  
  
-   `_exception_code()`예외 필터 외부 또는 `__except` 블록  
  
-   `_exception_info()`예외 필터 외부  
  
-   `_abnormal_termination()`외부는 `__finally` 블록  
  
 이 오류를 해결 하려면 예외 처리 내장 함수는 적절 한 컨텍스트에서 배치 됩니다 해야 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2707 오류가 발생 합니다.  
  
```  
// C2707.cpp  
#include <windows.h>  
#include <stdio.h>  
  
LONG MyFilter(LONG excode)   
{  
    return (excode == EXCEPTION_ACCESS_VIOLATION ?  
        EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);   // OK  
}  
  
LONG func(void)   
{  
    int x, y;  
    return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ?  // C2707  
             EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
  
    __try   
    {  
        y = 0;  
        x = 4 / y;  
        return 0;  
     }  
  
    __except(MyFilter(GetExceptionCode()))   
    {  
        return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ? // ok  
               EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
    }  
}  
  
int main()   
{  
    __try   
    {  
        func();  
    } __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf_s("Caught exception\n");  
    }  
}  
```