---
title: "컴파일러 오류 C2718 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2718"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2718"
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2718
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter': \_\_declspec\(align\('\#'\)\)를 사용하는 실제 매개 변수가 정렬되지 않았습니다.  
  
 함수 매개 변수에 [align](../../cpp/align-cpp.md) `__declspec` 한정자를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2718 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2718.cpp  
typedef struct __declspec(align(32)) AlignedStruct  {   
   int i;   
} AlignedStruct;  
  
void f2(int i, ...);  
  
void f4() {  
   AlignedStruct as;  
  
   f2(0, as);   // C2718, actual parameter is aligned  
}  
```