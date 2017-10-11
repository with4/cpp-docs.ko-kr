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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1dd522a3997e8b95409c9a6089bfdfd3d69a7af2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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

