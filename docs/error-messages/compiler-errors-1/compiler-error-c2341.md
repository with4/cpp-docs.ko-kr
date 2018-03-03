---
title: "컴파일러 오류 C2341 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03ceeb7f34ca7aca58151174c327161b18f3678f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2341"></a>컴파일러 오류 C2341
'섹션 이름': 사용 하도록 #pragma data_seg, code_seg 또는 section을 사용 하 여 세그먼트를 정의 해야 합니다  
  
 [할당](../../cpp/allocate.md) 문이 참조 하 여 정의 하지 않은 세그먼트 [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), 또는 [섹션](../../preprocessor/section.md) pragma입니다.  
  
 다음 샘플에서는 C2341 오류가 생성 됩니다.  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 해결 방법:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```