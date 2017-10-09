---
title: "컴파일러 오류 C2234 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2234
dev_langs:
- C++
helpviewer_keywords:
- C2234
ms.assetid: cfa42458-c803-4717-a017-9eca1c0cbfb0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b556efc1e73ae04f749441e1888d46cd5499e8ea
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2234"></a>컴파일러 오류 C2234
'name': 참조 배열이 적합 하지 않습니다.  
  
 참조에 대 한 포인터는 허용 되지 않으므로 참조 배열을 사용할 수 없는 합니다.  
  
 다음 샘플에서는 C2234 오류가 생성 됩니다.  
  
```  
// C2234.cpp  
int main() {  
   int i = 0, j = 0, k = 0, l = 0;  
   int &array[4] = {i,j,k,l};   // C2234  
   int array2[4] = {i,j,k,l};   // OK  
}  
```
