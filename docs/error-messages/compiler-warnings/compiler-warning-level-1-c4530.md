---
title: "컴파일러 경고 (수준 1) C4530 | Microsoft Docs"
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
  - "C4530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4530"
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ 예외 처리기가 사용되었지만 해제 의미 체계가 활성화되지 않았습니다.\/EHsc를 지정하십시오.  
  
 C\+\+ 예외 처리를 사용했지만 [\/EHsc](../../build/reference/eh-exception-handling-model.md)를 선택하지 않았습니다.  
  
 \/EHsc 옵션이 활성화되어 있지 않을 때 프레임에 자동 저장소가 있는 개체는 throw하고 있는 함수와 throw를 catch하고 있는 함수 사이에서 소멸되지 않습니다.  그러나 **try** 또는 **catch** 블록에 만들어진 자동 저장소가 있는 개체는 소멸됩니다.  
  
 다음 샘플에서는 C4530 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 이 경고를 해결하려면 \/EHsc를 사용하여 샘플을 컴파일합니다.