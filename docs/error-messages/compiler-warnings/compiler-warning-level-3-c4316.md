---
title: "컴파일러 경고(수준 3) C4316 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4316"
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 경고(수준 3) C4316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙에 할당된 객체는 이 유형에 정렬되지 않을 수 있습니다.  
  
 `operator new`를 사용하여 할당된 과도하게 정렬된 개체에는 지정된 맞춤이 없을 수 있습니다.  맞춤 정렬 루틴을 사용하도록 과도하게 정렬된 형식에 대해 [연산자 new](../../c-runtime-library/operator-new-crt.md) 및 [연산자 delete](../../c-runtime-library/operator-delete-crt.md)를 재정의합니다\(예: [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) 및 [\_aligned\_free](../../c-runtime-library/reference/aligned-free.md)\).  다음 샘플에서는 C4316 오류가 발생하는 경우를 보여 줍니다.  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```