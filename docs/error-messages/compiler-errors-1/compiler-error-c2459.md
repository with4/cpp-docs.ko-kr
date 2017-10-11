---
title: "컴파일러 오류 C2459 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2459
dev_langs:
- C++
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 78d92952b53c15d6170b32a711848111a4b6fd28
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2459"></a>컴파일러 오류 C2459
'identifier': 정의 하 고 있습니다. 익명 멤버로 서 추가할 수 없습니다.  
  
 클래스, 구조체 또는 공용 구조체는 자체 범위에서 익명 공용 구조체의 멤버에 의해 재정의 됩니다.  
  
 다음 샘플에서는 C2459 오류가 생성 됩니다.  
  
```  
// C2459.cpp  
// compile with: /c  
class C {  
   union { int C; };   // C2459  
   union { int D; };  
};  
```
