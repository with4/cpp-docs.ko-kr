---
title: "컴파일러 오류 C3632 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3632"
ms.assetid: a04e3217-f5a1-4461-a1db-d69fd096d468
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': construct에 대한 이벤트 스타일이 잘못되었습니다.  
  
 [\_\_event](../../cpp/event.md) 선언이 모든 구문에서 올바르지 않습니다.  
  
 C3632는 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3632 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3632.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc __interface I  
{  
   __event void sna();   // C3632  
};  
  
// use the following as an example  
__delegate void MyDel();  
public __gc __interface I2  
{  
   __event MyDel* sna;  
};  
  
int main()  
{  
}  
```