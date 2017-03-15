---
title: "컴파일러 오류 C3174 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3174"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3174"
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3174
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모듈 특성을 지정하지 않았습니다.  
  
 Visual C\+\+ 특성을 사용하는 프로그램에서 특성을 사용하는 프로그램에 필요한 [module](../../windows/module-cpp.md) 특성을 사용하지 않았습니다.  
  
 다음 샘플에서는 C3174 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```