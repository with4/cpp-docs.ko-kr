---
title: "컴파일러 오류 C2233 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2233
dev_langs:
- C++
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b83a0036667ed0bb7e30cc140cb3d4c38c5712b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2233"></a>컴파일러 오류 C2233
'identifier': 크기가 0 인 배열이 포함 된 개체의 배열을 사용할 수 없습니다  
  
 배열에 있는 각 개체에는 요소가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2233 오류가 생성 됩니다.  
  
```  
// C2233.cpp  
// compile with: /c  
class A {  
   char somearray[1];  
};  
  
class B {  
   char zeroarray[];  
};  
  
A array[100];   // OK  
B array2[100];   // C2233  
```