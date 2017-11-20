---
title: "컴파일러 오류 C2534 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2534
dev_langs: C++
helpviewer_keywords: C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee5b0e009833ca4f67f87bb234881b044215d5f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2534"></a>컴파일러 오류 C2534
'identifier': 생성자는 값을 반환할 수 없습니다  
  
 생성자는 값을 반환 하거나 반환 형식을 가질 수 없습니다 (아니더라도 `void` 반환 형식).  
  
 제거 하 여이 오류를 해결할 수 있습니다는 `return` 생성자 정의에서 문입니다.  
  
 다음 샘플에서는 C2534 오류가 생성 됩니다.  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```