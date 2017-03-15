---
title: "컴파일러 오류 C3272 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: a5d67c0228158e13090204954d8346e6656b4065
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3272"></a>컴파일러 오류 C3272
'symbol': 기호는 StructLayout(LayoutKind::Explicit)으로 정의된 typename 형식의 멤버이므로 FieldOffset이 필요합니다.  
  
때 `StructLayout(LayoutKind::Explicit)` 으로 필드를 표시 해야 실제로 `FieldOffset`합니다.  
  
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

