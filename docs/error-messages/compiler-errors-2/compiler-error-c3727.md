---
title: "컴파일러 오류 C3727 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3727"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3727"
ms.assetid: 17b9fe7b-ee9e-483f-9c27-1f709255a9e0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3727
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': 관리되는 이벤트는 대리자에 대한 포인터인 멤버 함수 또는 데이터 멤버이어야 합니다.  
  
 .NET 이벤트는 대리자 형식에 대한 포인터여야 합니다.  
  
 다음 샘플에서는 C3727 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3727.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class PseudoDelegate  
{  
};  
  
// use the following declaration to resolve the error.  
// __delegate void PseudoDelegate(int);  
  
__gc class MyAttr  
{  
   __event PseudoDelegate* MyE;  
};   // C3727  
  
int main()  
{  
}  
```