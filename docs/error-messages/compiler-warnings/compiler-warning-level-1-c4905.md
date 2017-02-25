---
title: "컴파일러 경고 (수준 1) C4905 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4905"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4905"
ms.assetid: 40240bf4-b14e-4c22-aeb2-52f2851532f6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4905
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자열 리터럴을 'LPSTR'로 캐스팅했습니다.  
  
 컴파일러에서 안전하지 않은 캐스트를 발견했습니다.  캐스트가 성공했지만 변환 루틴을 사용해야 합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4905 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4905.cpp  
// compile with: /W1  
#pragma warning(default : 4905)  
#include <windows.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
    LPSTR y = (LPSTR)L"1234";   // C4905  
  
    // try the following lines instead  
    // wchar_t y[128];  
    // size_t  sizeOfConverted;  
    // errcode err = 0;  
    //  
    // err = mbstowcs_s(&sizeOfConverted, &y[0], 128, "12345", 4);  
    // if (err != 0)  
    // {  
    //     printf_s("mbstowcs_s failed!");  
    //     exit (-1);  
    // }  
    // wprintf(L"%s\n", y);  
  
    return 0;  
}  
```