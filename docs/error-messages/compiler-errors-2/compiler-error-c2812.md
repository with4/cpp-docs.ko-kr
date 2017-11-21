---
title: "컴파일러 오류 C2812 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2812
dev_langs: C++
helpviewer_keywords: C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 859d371d5886ece416ea6d60c405b114a527864f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2812"></a>컴파일러 오류 C2812
\#/clr을 사용한 가져오기가 지원 되지 않습니다: pure 및 /clr: safe  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 [#import 지시문](../../preprocessor/hash-import-directive-cpp.md) 지원 되지 않습니다 **/clr: pure** 및 **/clr: safe** 때문에 `#import` 네이티브 컴파일러 지원 라이브러리를 사용 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2812 오류가 발생 합니다.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```