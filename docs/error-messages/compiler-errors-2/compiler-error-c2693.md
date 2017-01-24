---
title: "컴파일러 오류 C2693 | Microsoft Docs"
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
  - "C2693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2693"
ms.assetid: b7364ca8-b6be-48c0-97d6-6029787fb171
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 관리되는 배열 또는 WinRT 배열에 대한 참조 비교가 잘못되었습니다.  
  
 관리되는 배열 또는 WinRT 배열에 다름이 있는지 테스트할 수 없습니다.  예를 들어 관리되는 배열이 같은지 테스트로 확인할 수 있지만 한 배열이 다른 배열보다 크거나 작은지 테스트로 확인할 수는 없습니다.  
  
 **Managed Extensions for C\+\+**  
  
 [\_\_gc](../../misc/gc.md) 배열에 다름이 있는지 테스트할 수 없습니다.  예를 들어 관리되는 배열이 같은지 테스트로 확인할 수 있지만 한 배열이 다른 배열보다 크거나 작은지 테스트로 확인할 수는 없습니다.  
  
 다음 샘플에서는 C2693 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2693b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
int func3(int a __gc[], int b __gc[]) {  
   return a < b;    // C2693  
}  
int func1(int a __gc[], int b __gc[]) {  
   return a != b;   // OK  
}  
  
int func2(int a __gc[], int b __gc[]) {  
   return a == b;   // OK  
}  
```