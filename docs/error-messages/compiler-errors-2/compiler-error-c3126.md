---
title: 컴파일러 오류 C3126 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3126
dev_langs:
- C++
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 811377ef557cb690dcd8f1cf92b983d9bac60675
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3126"></a>컴파일러 오류 C3126
관리 되는 형식 'type' 내부 ' union' 공용 구조체를 정의할 수 없습니다.  
  
 관리 되는 형식 내 공용 구조체를 정의할 수 없습니다.  
  
 다음 샘플에서는 C3126 오류가 생성 됩니다.  
  
```  
// C3126_2.cpp  
// compile with: /clr /c  
ref class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```  
