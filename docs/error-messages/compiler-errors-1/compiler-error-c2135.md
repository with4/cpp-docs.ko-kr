---
title: "컴파일러 오류 C2135 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2135
dev_langs: C++
helpviewer_keywords: C2135
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d76a388ad34eb44d8c4bba0d0663115048ad41f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2135"></a>컴파일러 오류 C2135
'비트 연산자': 비트 필드 연산이 잘못되었습니다.  
  
 address-of 연산자(`&`)는 비트 필드에 적용할 수 없습니다.  
  
 다음 샘플에서는 C2135를 생성합니다.  
  
```  
// C2135.cpp  
struct S {  
   int i : 1;  
};  
  
struct T {  
   int j;  
};  
int main() {  
   &S::i;   // C2135 address of a bit field  
   &T::j;   // OK  
}  
```