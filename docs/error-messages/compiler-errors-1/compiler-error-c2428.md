---
title: "컴파일러 오류 C2428 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2428
dev_langs:
- C++
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: acc73e232e6e513df394875ec93cfa34911e2760
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2428"></a>컴파일러 오류 C2428
'operation': 'bool' 형식의 피연산자에 사용할 수 없습니다  
  
 형식의 개체에 감소 연산자를 적용할 수 없습니다 `bool`합니다.  
  
 다음 샘플에서는 C2428 오류가 생성 됩니다.  
  
```  
// C2428.cpp  
void g(bool fFlag) {  
   --fFlag;   // C2428  
   fFlag--;   // C2428  
}  
```
