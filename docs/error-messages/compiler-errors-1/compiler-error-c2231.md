---
title: "컴파일러 오류 C2231 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2231
dev_langs: C++
helpviewer_keywords: C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f55b9c703c9a427a05b8b57f9b4d6c14db63166
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2231"></a>컴파일러 오류 C2231
'.': 왼쪽 피연산자 포인트 s-k'를 사용 하세요. '->'  
  
 멤버 선택 연산 (.)의 왼쪽에 있는 피연산자는 클래스, 구조체 또는 공용 구조체 대신 포인터입니다.  
  
 다음 샘플에서는 C2231을 생성합니다.  
  
```  
// C2231.c  
struct S {  
   int member;  
} s, *ps = &s;  
int main() {  
   ps.member = 0;   // C2231  
  
   // OK  
   ps->member = 0;   // crash  
   s.member = 0;  
}  
```