---
title: 컴파일러 오류 C2101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2101
dev_langs:
- C++
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16402a2e49d1a71ba7b246569a77a65aee7ff3bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165076"
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