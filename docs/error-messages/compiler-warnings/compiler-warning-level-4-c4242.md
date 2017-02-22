---
title: "컴파일러 경고 (수준 4) C4242 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4242"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4242"
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고 (수준 4) C4242
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'type1'에서 'type2'\(으\)로 변환하면서 데이터가 손실될 수 있습니다.  
  
 형식이 서로 다릅니다.  형식을 변환하면 데이터가 손실될 수 있는 상태에서  컴파일러가 형식을 변환했습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 C4242에 대한 추가 정보는 [Common Compiler Errors](http://msdn.microsoft.com/library/windows/desktop/aa384160)를 참조하십시오.  
  
 다음 샘플에서는 C4242 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```