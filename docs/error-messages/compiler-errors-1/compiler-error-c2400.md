---
title: "컴파일러 오류 C2400 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2400
dev_langs: C++
helpviewer_keywords: C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b819c81a3475a541fb672094bbdfa62b2fcfe6d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2400"></a>컴파일러 오류 C2400
인라인 어셈블러 구문 오류가 '컨텍스트의'; 'token'를 찾을 수합니다  
  
 지정된 된 컨텍스트에 구문 오류가 발생 하는 토큰입니다.  
  
 다음 샘플에서는 C2400 오류가 생성 됩니다.  
  
```  
// C2400.cpp  
// processor: x86  
int main() {  
   __asm {  
      heh ax,bx;   // C2400, heh is not a valid x86 instruction  
      mov ax,bx;   // OK  
   }  
}  
```