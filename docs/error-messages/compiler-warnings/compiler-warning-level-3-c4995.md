---
title: "컴파일러 경고 (수준 3) C4995 | Microsoft Docs"
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
  - "C4995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4995"
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 이름이 \#pragma deprecated로 표시되었습니다.  
  
 컴파일러에서 pragma [deprecated](../../preprocessor/deprecated-c-cpp.md)로 표시한 함수를 발견했습니다.  이 함수는 이후 릴리스에서 제공되지 않을 수 있습니다.  다음 예제와 같이 [warning](../../preprocessor/warning.md) pragma를 사용하여 이 경고를 해제할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C4995 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```