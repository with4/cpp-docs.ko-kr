---
title: "컴파일러 오류 C2624 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2624
dev_langs:
- C++
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c70165fc0d57d753dadd2bed207a00e3dd3498aa
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2624"></a>컴파일러 오류 C2624
'extern' 변수를 선언 하는 로컬 클래스를 사용할 수 없습니다.  
  
 지역 클래스 또는 구조체 선언에 사용할 수 없습니다 `extern` 변수입니다.  
  
 다음 샘플에서는 C2624 오류가 생성 됩니다.  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```
