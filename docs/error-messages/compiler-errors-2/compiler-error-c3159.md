---
title: "컴파일러 오류 C3159 | Microsoft Docs"
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
  - "C3159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3159"
ms.assetid: e115cc76-0021-4568-95fd-61a324c41a85
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointer' : 값 형식에 대한 포인터 배열을 선언할 수 없습니다.  
  
 값 형식에 대한 포인터 배열을 선언할 수 없습니다.  
  
 C3159는 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3159 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3159.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value struct B {  
};  
  
void f( B*[] );   // C3159  
  
int main() {  
}  
```