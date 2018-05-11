---
title: 컴파일러 오류 C2570 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b870ddd8bb162f4f65bd3200c397f912249304b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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