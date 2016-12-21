---
title: "컴파일러 경고 (수준 4) C4210 | Microsoft Docs"
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
  - "C4210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4210"
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 함수에서 파일 범위를 제공했습니다.  
  
 기본 Microsoft 확장\([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\)을 사용하여 함수에서 파일 범위를 선언했습니다.  
  
```  
// C4210.c  
// compile with: /W4 /c  
void func1()  
{  
   extern int func2( double );   // C4210 expected  
}  
  
int main()  
{  
   func2( 4 );   //  /Ze passes 4 as type double  
}                //  /Za passes 4 as type int  
```  
  
 이러한 확장을 사용하면 코드를 다른 컴파일러로 옮길 수 없습니다.