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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5f214109a6e7838ad0964f912feea78c6e5e9c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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