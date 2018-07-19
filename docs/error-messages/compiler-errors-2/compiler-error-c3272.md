---
title: 컴파일러 오류 C3272 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39900d11e7f6be25e8c9b701a52ff726807a4828
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254159"
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
