---
title: "컴파일러 오류 C2762 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2762
dev_langs: C++
helpviewer_keywords: C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15e96c7df9d407bcb3b0b5686b83c5e8c42c33fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2762"></a>컴파일러 오류 C2762
'class': 'argument'에 대 한 템플릿 인수로 잘못 된 식  
  
 사용 하는 경우 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 컴파일러는 포인터에 정수 계열 변환 하지 않습니다.  
  
 다음 샘플에서는 C2762 오류가 생성 됩니다.  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```