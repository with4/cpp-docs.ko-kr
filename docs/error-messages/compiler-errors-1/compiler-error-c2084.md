---
title: "컴파일러 오류 C2084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2084"
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' 함수에 이미 본문이 있습니다.  
  
 함수가 이미 정의되었습니다.  
  
 이전 버전의 Visual C\+\+에서는  
  
-   추가 정의를 사용할 수 없는 경우에도 컴파일러에서 실제로는 형식이 같은 복수 템플릿 특수화를 허용했습니다.  이제는 컴파일러에서 이러한 복수 정의를 발견할 수 있습니다.  
  
-   \_\_int32와 int가 별도의 형식으로 간주되었습니다.  이제는 컴파일러에서 \_\_int32를 int의 동의어로 간주합니다.  따라서 함수가 \_\_int32와 int 둘 다에 대해 오버로드된 경우에는 컴파일러에서 복수 정의를 발견하고 오류를 발생시킵니다.  
  
 다음 샘플에서는 C2084 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```