---
title: "컴파일러 경고 (수준 2) C4156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4156"
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 2) C4156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delete' 배열 형식을 사용하지 않고 배열 식을 삭제했습니다. 배열 형식이 대체됩니다.  
  
 비배열 형식의 **delete**는 배열을 삭제할 수 없습니다.  컴파일러가 **delete**를 배열 형식으로 변환했습니다.  
  
 이 경고는 Microsoft 확장\(\/Ze\)에서만 발생합니다.  
  
## 예제  
  
```  
// C4156.cpp  
// compile with: /W2  
int main()  
{  
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];  
   delete array; // C4156, changed by compiler to "delete [] array;"  
}  
```