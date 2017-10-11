---
title: "컴파일러 오류 C3272 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8447e7eb07cea90da5076fa2c7bf6fe950baf5e5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3272"></a>컴파일러 오류 C3272
'symbol': 기호는 StructLayout(LayoutKind::Explicit)으로 정의된 typename 형식의 멤버이므로 FieldOffset이 필요합니다.  
  
때 `StructLayout(LayoutKind::Explicit)` 필드 표시 되어야 합니다가 적용 된 경우 `FieldOffset`합니다.  
  
다음 샘플에서는 C3272를 생성합니다.  
  
```  
// C3272_2.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Explicit)]  
ref struct X  
{  
   int data_;   // C3272  
   // try the following line instead  
   // [FieldOffset(0)] int data_;  
};  
```  

