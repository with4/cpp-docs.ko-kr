---
title: "컴파일러 오류 C2118 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2118
dev_langs:
- C++
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d09ed769975b522b0b881148ed684a99552bb099
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2118"></a>컴파일러 오류 C2118
음수 아래 첨자  
  
 배열 크기를 정의 값이 최대 배열 크기 보다 큰 또는 0 보다 작습니다.  
  
 다음 샘플에서는 C2118 오류가 생성 됩니다.  
  
```  
// C2118.cpp  
int main() {  
   int array1[-1];   // C2118  
   int array2[3];   // OK  
}  
```
