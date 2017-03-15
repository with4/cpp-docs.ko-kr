---
title: "컴파일러 경고 (수준 4) C4400 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4400"
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 경고 (수준 4) C4400
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 이 형식에 대해서는 const\/volatile 한정자를 사용할 수 없습니다.  
  
 [const](../../cpp/const-cpp.md) 및 [volatile](../../cpp/volatile-cpp.md) 한정자는 공용 언어 런타임 형식의 변수와 함께 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C4400 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4400.cpp  
// compile with: /clr /W4  
// C4401 expected  
using namespace System;  
#pragma warning (disable : 4101)  
int main() {  
   const String^ str;   // C4400  
   volatile String^ str2;   // C4400  
}  
```