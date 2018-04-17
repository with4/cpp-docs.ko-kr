---
title: 컴파일러 오류 C2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c23e188db9e811122102259f5fa93733d29f00f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2001"></a>컴파일러 오류 C2001
상수에 줄 바꿈  
  
 다음을 수행 하지 않는 한 두 번째 줄에는 문자열 상수를 계속할 수 없습니다.  
  
-   백슬래시로 첫 번째 줄의 끝입니다.  
  
-   큰따옴표와 첫 번째 줄에 문자열을 닫고 다시 큰따옴표와 다음 줄에서 문자열을 엽니다.  
  
 \N 첫 번째 줄 끝 충분 하지 않습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2001 오류가 생성 됩니다.  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## <a name="example"></a>예  
 문자열 상수에 줄 연속 문자 뒤의 다음 줄의 시작 부분에 공백은 포함 됩니다. None 위에 표시 된 예에서는 문자열 상수에 줄 바꿈 문자를 포함 합니다. 다음과 같이 줄 바꿈 문자를 포함할 수 있습니다.  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```