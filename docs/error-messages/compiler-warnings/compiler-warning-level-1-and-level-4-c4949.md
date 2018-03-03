---
title: "컴파일러 경고 (수준 1 및 수준 4) C4949 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d23a6d6e030007289cc50ce0372acc8f99e7ed3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>컴파일러 경고(수준 1 및 수준 4) C4949
pragma 'managed' 및 'u'로 컴파일하는 경우에 의미 있는 ' / clr [: 옵션]'  
  
 컴파일러에서 무시 된 [관리](../../preprocessor/managed-unmanaged.md) 와 소스 코드와 컴파일되지 않은 경우 pragma는 관리 되지 않는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다. 이 경고는 정보 제공용입니다.  
  
 다음 샘플에서는 C4949 오류가 생성 됩니다.  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 때 **관리 되지 않는 #pragma** 없이 사용 **/clr**, C4949 수준 4 경고입니다.  
  
 다음 샘플에서는 C4949 오류가 생성 됩니다.  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```