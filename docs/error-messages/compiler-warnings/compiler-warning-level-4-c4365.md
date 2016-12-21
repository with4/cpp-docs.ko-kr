---
title: "컴파일러 경고 (수준 4) C4365 | Microsoft Docs"
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
  - "C4365"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4365"
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4365
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'action' : 'type\_1'에서 'type\_2'\(으\)로의 변환입니다. signed 또는 unsigned가 일치하지 않습니다.  
  
 예를 들어, unsigned 값을 signed 값으로 변환하려고 했습니다.  
  
 C4365는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4365 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4365.cpp  
// compile with: /W4  
#pragma warning(default:4365)  
  
int f(int) { return 0; }  
void Test(size_t i) {}  
  
int main() {  
   unsigned int n = 10;  
   int o = 10;  
   n++;  
   f(n);   // C4365  
   f(o);   // OK  
  
   Test( -19 );   // C4365  
}  
```