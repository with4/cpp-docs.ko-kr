---
title: "컴파일러 경고 (수준 4) C4001 | Microsoft Docs"
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
  - "C4001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4001"
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장인 '한 줄로 된 주석'을 사용했습니다.  
  
 한 줄로 된 주석은 C\+\+에서는 표준이며 C에서는 표준이 아닙니다.  엄격한 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서 한 줄로 된 주석을 포함하는 C 파일은 비표준 확장의 사용으로 인해 C4001을 발생시킵니다.  한 줄로 된 주석은 C\+\+에서 표준이므로 Microsoft 확장\(\/Ze\)으로 컴파일할 경우 한 줄로 된 주석을 포함하는 C 파일은 C4001을 발생시키지 않습니다.  
  
## 예제  
 경고를 사용하지 않으려면 [\#pragma warning\(disable:4001\)](../../preprocessor/warning.md)의 주석 처리를 제거합니다.  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```