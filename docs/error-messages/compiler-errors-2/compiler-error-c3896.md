---
title: 컴파일러 오류 C3896 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc60c09d6fd99e56f0261409099e56713604a76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269740"
---
# <a name="compiler-error-c3896"></a>컴파일러 오류 C3896
'member': 잘못 된 이니셜라이저:이 리터럴 데이터 멤버는 'nullptr'로 초기화할 수 있습니다  
  
 A [리터럴](../../windows/literal-cpp-component-extensions.md) 데이터 멤버 잘못 초기화 되었습니다.  참조 [nullptr](../../windows/nullptr-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
 다음 샘플에서는 C3896 오류가 생성 됩니다.  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```