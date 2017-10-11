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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5460ff70c95fd593539a16140c52fa1490bffc4e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
