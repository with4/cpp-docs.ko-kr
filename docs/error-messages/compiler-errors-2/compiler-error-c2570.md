---
title: "컴파일러 오류 C2570 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6b5d53463e889504f202b7d50b8c5ac877f27cf8
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2570"></a>컴파일러 오류 C2570
'identifier': 공용 구조체는 기본 클래스를 사용할 수 없습니다  
  
 공용 구조체는 클래스, 구조체 또는 공용 구조체에서 파생 됩니다. 이것은 허용되지 않습니다. 대신 파생 된 형식으로 클래스 또는 구조체 선언 하십시오.  
  
 다음 샘플에서는 C2570 오류가 생성 됩니다.  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```
