---
title: "컴파일러 오류 C2258 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2258
dev_langs: C++
helpviewer_keywords: C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86b4d96da58b33a62baf2f2587146563a4f0ed55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2258"></a>컴파일러 오류 C2258
순수 구문이 잘못되었습니다. '= 0'이어야 합니다.  
  
 순수 가상 함수를 잘못된 구문으로 선언했습니다.  
  
 다음 샘플에서는 C2258을 생성합니다.  
  
```  
// C2258.cpp  
// compile with: /c  
class A {  
public:  
   void virtual func1() = 1; // C2258  
   void virtual func2() = 0;   // OK  
};  
```