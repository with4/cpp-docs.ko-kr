---
title: "컴파일러 오류 C2438 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2438
dev_langs: C++
helpviewer_keywords: C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dda1d429c785a5def5c2e596085e700370f37c60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2438"></a>컴파일러 오류 C2438
'identifier': 생성자를 통해 정적 클래스 데이터를 초기화할 수 없습니다  
  
 클래스의 정적 멤버를 초기화 하는 생성자 사용 됩니다. 클래스 선언 외부 정의에서 정적 멤버를 초기화 합니다.  
  
 다음 샘플에서는 C2438 오류가 생성 됩니다.  
  
```  
// C2438.cpp  
struct X {  
   X(int i) : j(i) {}   // C2438  
   static int j;  
};  
  
int X::j;  
  
int main() {  
   X::j = 1;  
}  
```