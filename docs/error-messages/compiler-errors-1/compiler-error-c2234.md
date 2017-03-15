---
title: "컴파일러 오류 C2234 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2234"
ms.assetid: cfa42458-c803-4717-a017-9eca1c0cbfb0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 참조 배열이 잘못되었습니다.  
  
 참조에 대한 포인터를 사용할 수 없으므로 참조 배열을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2234 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2234.cpp  
int main() {  
   int i = 0, j = 0, k = 0, l = 0;  
   int &array[4] = {i,j,k,l};   // C2234  
   int array2[4] = {i,j,k,l};   // OK  
}  
```