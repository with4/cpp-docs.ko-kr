---
title: "컴파일러 오류 C3641 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 145d1739752f96b35cbf9af51c81900ab66fe6c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3641"></a>컴파일러 오류 C3641
'function': 잘못 된 호출 규칙 'calling_convention' /clr을 사용 하 여 컴파일된 함수에 대 한: pure 또는 /clr: safe  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 만 [__clrcall](../../cpp/clrcall.md) 호출 규칙은 사용할 수 [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 다음 샘플에서는 C3641 오류가 생성 됩니다.  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```