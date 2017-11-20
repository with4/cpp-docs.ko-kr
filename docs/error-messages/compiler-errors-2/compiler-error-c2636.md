---
title: "컴파일러 오류 C2636 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2636
dev_langs: C++
helpviewer_keywords: C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9aa491ec27c59a6fdc336a9ab148806e468a4aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2636"></a>컴파일러 오류 C2636
'identifier': 참조 멤버에 대 한 포인터가 잘못 되었습니다  
  
 참조 멤버에 대 한 포인터를 선언 했습니다.  
  
 다음 샘플에서는 C2636 오류가 생성 됩니다.  
  
```  
// C2636.cpp  
struct S {};  
int main() {  
   int &S::*prs;   // C2636  
   int S::*prs1;   // OK  
   int *S::*prs2;   // OK  
}  
```