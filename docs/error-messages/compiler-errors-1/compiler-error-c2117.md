---
title: "컴파일러 오류 C2117 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2117
dev_langs:
- C++
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3e326e7a7dde296439d1a9c24c1d042af63dc6f9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2117"></a>컴파일러 오류 C2117
'identifier': 배열 범위 오버플로입니다  
  
 배열에 이니셜라이저가 너무 많습니다.  
  
-   배열 요소와 이니셜라이저의 크기 및 수량이 일치 하지 않습니다.  
  
-   문자열에 null 종결자를 위한 공간이 없습니다.  
  
 다음 샘플에서는 C2117 오류가 생성 됩니다.  
  
```  
// C2117.cpp  
int main() {  
   char abc[4] = "abcd";   // C2117  
   char def[4] = "abd";   // OK  
}  
```
