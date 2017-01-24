---
title: "컴파일러 오류 C3531 | Microsoft Docs"
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
  - "C3531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3531"
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'기호': 'auto'가 포함된 형식의 기호에는 이니셜라이저가 있어야 합니다.  
  
 지정된 변수에 이니셜라이저 식이 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  변수를 선언할 때 등호\(\=\) 구문을 사용하는 단순 할당과 같은 이니셜라이저 식을 지정합니다.  
  
## 예제  
 다음 예제에서는 `x1`, `y1, y2, y3` 및 `z2` 변수가 초기화되지 않기 때문에 C3531이 발생합니다.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)