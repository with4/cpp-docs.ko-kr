---
title: "컴파일러 오류 C2232 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2232
dev_langs:
- C++
helpviewer_keywords:
- C2232
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70ccba95ad86e99d48e49e4cf3de80066395ae5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2232"></a>컴파일러 오류 C2232
'->': 왼쪽된 피연산자에 's k ' 형식에서 사용 하 여'.'  
  
 `->` 연산자의 왼쪽에 있는 피연산자가 포인터가 아닙니다. 마침표 (.) 연산자를 사용 하 여 클래스, 구조체 또는 공용 구조체에 대 한 합니다.  
  
 다음 샘플에서는 C2232를 생성합니다.  
  
```  
// C2232.c  
struct X {  
    int member;  
} x, *px;  
int main() {  
    x->member = 0;   // C2232, x is not a pointer  
  
    px->member = 0;  
    x.member = 0;  
}  
```