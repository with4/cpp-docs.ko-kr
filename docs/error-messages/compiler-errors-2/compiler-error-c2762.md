---
title: "컴파일러 오류 C2762 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2762
dev_langs:
- C++
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e121ab82b8e49fb1727e626eea7d060e8def2b8c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
