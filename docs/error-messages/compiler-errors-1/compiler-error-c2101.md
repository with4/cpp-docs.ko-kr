---
title: "컴파일러 오류 C2101 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2101
dev_langs: C++
helpviewer_keywords: C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 65b63962ebdc073ab6ecb68de5251d9e1eae8399
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2101"></a>컴파일러 오류 C2101
상수에 '&'가 있습니다.  
  
 연산자 주소( `&` )에 피연산자로 l 값이 있어야 합니다.  
  
 다음 샘플에서는 C2101을 생성합니다.  
  
```  
// C2101.cpp  
int main() {  
   char test;  
   test = &'a';   // C2101  
   test = 'a';   // OK  
}  
```