---
title: 컴파일러 오류 C3183 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3183
dev_langs:
- C++
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4520922550dfcb5050c5e8a122910acf4b124934
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252473"
---
# <a name="compiler-error-c3183"></a>컴파일러 오류 C3183
WinRT 또는 관리되는 형식 'type' 내부에 명명되지 않은 클래스, 구조체 또는 공용 구조체를 정의할 수 없습니다.  
  
WinRT 또는 관리되는 형식에 포함된 형식의 이름을 지정해야 합니다.  
  
다음 샘플에서는 C3183 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3183a.cpp  
// compile with: /clr /c  
ref class Test  
{  
   ref class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
```  
