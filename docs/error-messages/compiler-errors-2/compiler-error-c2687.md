---
title: "컴파일러 오류 C2687 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2687"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2687"
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2687
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 예외 선언은 'void'일 수 없으며 불완전 형식 또는 불완전 형식에 대한 포인터 및 참조를 나타낼 수 없습니다.  
  
 예외 선언에 포함할 형식은 정의된 형식이어야 하고 void가 아니어야 합니다.  
  
 다음 샘플에서는 C2687 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```