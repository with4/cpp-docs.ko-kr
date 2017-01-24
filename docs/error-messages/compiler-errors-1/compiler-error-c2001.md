---
title: "컴파일러 오류 C2001 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2001"
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상수에 줄 바꿈 문자가 있습니다.  
  
 다음과 같이 입력해야 두 번째 줄에 계속해서 문자열 상수가 올 수 있습니다.  
  
-   첫 번째 줄 끝에 백슬래시를 입력합니다.  
  
-   첫 번째 줄의 문자열 끝에 큰따옴표를 입력하고 다음 줄의 문자열 앞에 또 하나의 큰따옴표를 입력합니다.  
  
 첫 번째 줄 끝에 \\n을 입력하는 것만으로는 부족합니다.  
  
## 예제  
 다음 샘플에서는 C2001 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
## 예제  
 다음 줄 시작 부분에서 줄 연속 문자 다음에 오는 공백은 문자열 상수에 포함됩니다.  위의 예제에서는 문자열 상수에 줄 바꿈 문자가 포함되어 있지 않지만,  아래에 있는 것처럼 줄 바꿈 문자를 포함할 수 있습니다.  
  
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