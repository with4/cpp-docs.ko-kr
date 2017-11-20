---
title: "컴파일러 오류 C2638 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2638
dev_langs: C++
helpviewer_keywords: C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f5eb7d56c715ade00d8aa4ca5c9e41a73441561
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2638"></a>컴파일러 오류 C2638
'identifier': __based 한정자를 멤버의 포인터  
  
 `__based` 멤버에 대 한 포인터에 대 한 한정자를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2638 오류가 생성 됩니다.  
  
```  
// C2638.cpp  
void *a;  
  
class C {  
public:  
   int i;  
   int j;  
   int func();  
};  
int __based (a) C::* cpi = &C::i;  // C2638  
int (__based (a) C::* cpf)() = &C::func; // c2638  
```