---
title: "컴파일러 경고 (수준 1) C4552 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4552
dev_langs:
- C++
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb12d5774094040a3caacba8c0cdfe8d8b604252
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4552"></a>컴파일러 경고(수준 1) C4552
'operator': 연산자에 영향을 주지 않습니다. 파생 작업이 있는 연산자 여야 합니다.  
  
 식 문의 top 식의 영향을 주지 쪽 연산자가 있으면 실수 한 부분 때문일 수 있습니다.  
  
 이 경고를 해결 하려면 괄호 안에 식을 삽입 합니다.  
  
 다음 샘플에서는 C4552 오류가 생성 됩니다.  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```