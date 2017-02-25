---
title: "컴파일러 경고 (수준 4) C4324 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4324"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4324"
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4324
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'struct\_name' : \_\_declspec\(align\(\)\) 때문에 구조가 채워졌습니다.  
  
 [\_\_declspec\(align\)](../../cpp/align-cpp.md) 값을 지정했으므로 구조의 끝에 여백이 추가되었습니다.  
  
 예를 들어, 다음 코드에서는 C4324 경고가 발생합니다.  
  
```  
// C4324.cpp  
// compile with: /W4  
struct __declspec(align(32)) A  
{  
   char a;  
};   // C4324  
  
int main()  
{  
}  
```