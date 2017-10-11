---
title: "컴파일러 오류 C2529 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2529
dev_langs:
- C++
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7c0a693af458818b8c5ac44e160272d8b15fa5f5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2529"></a>컴파일러 오류 C2529
'name': 참조에 대 한 참조가 잘못 되었습니다.  
  
 포인터 구문을 사용 하 고 포인터에 대 한 참조를 선언 하 여이 오류를 해결할 수 있습니다.  
  
 다음 샘플에서는 C2529 오류가 생성 됩니다.  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```
