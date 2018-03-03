---
title: "컴파일러 오류 C2389 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2389
dev_langs:
- C++
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba614bc13d593c455922c84aea2c76ad48890bb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2389"></a>컴파일러 오류 C2389
'operator': 'nullptr'는 잘못된 피연산자입니다.  
  
 `nullptr` 는 피연산자일 수 없습니다.  
  
 다음 샘플에서는 C2389를 생성합니다.  
  
```  
// C2389.cpp  
// compile with: /clr  
int main() {  
   throw nullptr;   // C2389  
}  
```