---
title: "컴파일러 오류 C2086 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 36270e50049889e5c6819a22b6b6e35d4c7d2caf
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2086"></a>컴파일러 오류 C2086
'identifier': 재정의  
  
 식별자가 두 번 이상 정의 하 또는 후속 선언 이전 쿼리와 다릅니다.  
  
 C2086 C# 어셈블리 참조에 대 한 증분 빌드의 결과로 될 수도 있습니다. 이 오류를 해결 하려면 C# 어셈블리를 다시 작성 합니다.  
  
 다음 샘플에서는 C2086 오류가 생성 됩니다.  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```
