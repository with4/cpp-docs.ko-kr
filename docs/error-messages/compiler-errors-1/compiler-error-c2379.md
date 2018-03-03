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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d39a94722563a9feef7914f092968f1754d0d429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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