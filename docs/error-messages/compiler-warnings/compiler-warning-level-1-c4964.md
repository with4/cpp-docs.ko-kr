---
title: "컴파일러 경고 (수준 1) C4964 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7483b82c363898bc16ed5fc7d48f9cf0b35c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4964"></a>컴파일러 경고(수준 1) C4964
최적화 옵션을 지정 합니다. 프로필 정보가 수집 되지 않습니다.  
  
 [/GL](../../build/reference/gl-whole-program-optimization.md) 및 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 지정 했지만 최적화가 없습니다. 요청 된.pgc 파일이 생성 되 고 따라서 없는 프로필 기반 최적화를 수행할 수 있도록 합니다.  
  
 응용 프로그램을 실행할 때 생성 되는.pgc 파일을 사용 하도록 하려는 경우 중 하나를 지정 된 [/O](../../build/reference/o-options-optimize-code.md) 컴파일러 옵션입니다.  
  
 다음 샘플에서는 C4964 오류가 생성 됩니다.  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```