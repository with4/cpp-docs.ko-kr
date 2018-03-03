---
title: "컴파일러 오류 C2137 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2137
dev_langs:
- C++
helpviewer_keywords:
- C2137
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d91420979ca9a7d2c3667aa7fa4664f09543ea8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2137"></a>컴파일러 오류 C2137
문자 상수가 비어 있습니다.  
  
 빈 문자 상수(' ')는 허용되지 않습니다.  
  
 다음 샘플에서는 C2137을 생성합니다.  
  
```  
// C2137.cpp  
int main() {  
   char c = '';   // C2137  
   char d = ' ';   // OK  
}  
```