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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72153d758fe1c6e1204f38de6dcefa35cb5387ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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