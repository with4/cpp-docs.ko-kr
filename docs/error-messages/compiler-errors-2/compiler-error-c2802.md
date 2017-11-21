---
title: "컴파일러 오류 C2802 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2802
dev_langs: C++
helpviewer_keywords: C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: adc1b4178caebe9893727aaf8ff802d6f030e986
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2802"></a>컴파일러 오류 C2802
정적 멤버 'operator 연산자'에 정식 매개 변수가 없습니다.  
  
 선언한 연산자는 `static` 멤버 함수는 매개 변수가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2802 오류가 생성 됩니다.  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```