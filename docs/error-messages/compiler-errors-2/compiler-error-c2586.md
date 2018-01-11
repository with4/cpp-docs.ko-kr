---
title: "컴파일러 오류 C2586 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2586
dev_langs: C++
helpviewer_keywords: C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fbdca0a5f1f90b82af908683e9cf506153f888c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2586"></a>컴파일러 오류 C2586
잘못 된 사용자 정의 변환 구문이: 간접 참조가 잘못 되었습니다  
  
 변환 연산자의 간접 참조는 허용 되지 않습니다.  
  
 다음 샘플에서는 C2586 오류가 생성 됩니다.  
  
```  
// c2586.cpp  
// compile with: /c  
struct C {  
   * operator int();   // C2586  
   operator char();   // OK  
};  
```