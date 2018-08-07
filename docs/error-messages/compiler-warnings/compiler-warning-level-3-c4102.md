---
title: 컴파일러 경고 (수준 3) C4102 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4102
dev_langs:
- C++
helpviewer_keywords:
- C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f3ee9f8e5c55c1963207b09ec58da0254ef448c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290415"
---
# <a name="compiler-warning-level-3-c4102"></a>컴파일러 경고(수준 3) C4102
'label': 참조되지 않은 레이블입니다.  
  
 레이블이 정의되었지만 참조되지 않습니다. 컴파일러는 레이블을 무시합니다.  
  
 다음 샘플에서는 C4102를 생성합니다.  
  
```  
// C4102.cpp  
// compile with: /W3  
int main() {  
   int a;  
  
   test:   // C4102, remove the unreferenced label to resolve  
  
   a = 1;  
}  
```