---
title: "컴파일러 오류 C2379 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 69be5132451269f7eba9c2e9186a9c25d4629ae7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2379"></a>컴파일러 오류 C2379
형식 매개 변수 번호의 형식이 다릅니다.  
  
 지정 된 매개 변수 형식의 기본 확장이 긴 하지만 이전 선언에 형식이 호환 되지 않습니다. 이것은 ANSI C에서 오류 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))에서는 경고 이며 Microsoft 확장명 (**/Ze**).  
  
 다음 샘플에서는 C2379 오류가 생성 됩니다.  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```
