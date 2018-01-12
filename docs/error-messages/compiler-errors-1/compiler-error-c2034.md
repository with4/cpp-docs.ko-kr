---
title: "컴파일러 오류 C2034 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2034
dev_langs: C++
helpviewer_keywords: C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9b1f80fcdd3fa8819fbd3d800aa4cfbd50e01c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2034"></a>컴파일러 오류 C2034
'identifier': 비트 수에 비해 너무 작음을 비트 필드의 유형  
  
 비트 필드 선언에는 비트 수는 기본 형식의 크기를 초과합니다.  
  
 다음 샘플에서는 C2034 오류가 생성 됩니다.  
  
```  
// C2034.cpp  
struct A {  
   char test : 9;   // C2034, char has 8 bits  
};  
```  
  
 해결 방법:  
  
```  
// C2034b.cpp  
// compile with: /c  
struct A {  
   char test : 8;  
};  
```