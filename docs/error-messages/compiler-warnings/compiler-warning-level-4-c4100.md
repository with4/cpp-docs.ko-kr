---
title: "컴파일러 경고(수준 4) C4100 | Microsoft Docs"
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
  - "C4100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4100"
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 참조되지 않은 정식 매개 변수  
  
 정식 매개 변수가 함수 본문에서 참조되지 않습니다.  참조되지 않은 매개 변수는 무시됩니다.  
  
 C4100은 코드가 기본 형식의 다른 참조되지 않은 매개 변수에서 소멸자를 호출할 경우에도 발생할 수 있습니다.  이것은 Visual C\+\+ 컴파일러의 제한 사항입니다.  
  
 다음 샘플에서는 C4100 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```