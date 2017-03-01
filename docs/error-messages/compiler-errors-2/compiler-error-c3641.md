---
title: "컴파일러 오류 C3641 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 1f928242a26ed45a48cc9bc19be231e2d0e09a51
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3641"></a>컴파일러 오류 C3641
'function': 잘못 된 호출 규칙 'calling_convention' /clr을 사용 하 여 컴파일된 함수에 대 한: pure 또는 /clr: safe  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
 만 [__clrcall](../../cpp/clrcall.md) 에서 허용 되는 호출 규칙 [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 다음 샘플에서는 C3641 오류가 생성 됩니다.  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```
