---
title: "컴파일러 오류 C2180 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2180
dev_langs: C++
helpviewer_keywords: C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fdea36a8c6c7bf5e561c161dc7180ab3b563c0ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2180"></a>컴파일러 오류 C2180
제어 식이 'type' 형식입니다.  
  
 `if`, `while`, `for` 또는 `do` 문의 제어 식은 `void`로 캐스팅되는 식입니다. 이 문제를 해결하려면 `bool` 또는 `bool`로 변환할 수 있는 형식을 생성하는 식으로 제어 식을 변경합니다.  
  
 다음 샘플에서는 C2180 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```