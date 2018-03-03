---
title: "컴파일러 오류 C3271 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3271
dev_langs:
- C++
helpviewer_keywords:
- C3271
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a102429fba0c001d0169e4e96003f86be05f4405
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3271"></a>컴파일러 오류 C3271
'member': FieldOffset 특성에 대한 값 'value'가 잘못되었습니다.  
  
 **FieldOffset** 특성에 음수가 전달되었습니다.  
  
 다음 샘플에서는 C3271을 생성합니다.  
  
```  
// C3271.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Explicit)]  
value class MyStruct1 {  
   public: [FieldOffset(0)] int a;  
   public: [FieldOffset(-1)] long b;   // C3271  
};  
```  
