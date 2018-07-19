---
title: 컴파일러 오류 C3626 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ede2ec42b3afc581126d2591cba072817dcc8748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266170"
---
# <a name="compiler-error-c3626"></a>컴파일러 오류 C3626
'keyword': '__event' 키워드는 COM 인터페이스, 멤버 함수 및 대리자에 대 한 포인터는 데이터 멤버에만 사용할 수 있습니다  
  
 키워드를 잘못 사용 되었습니다.  
  
 다음 샘플에서는 C3626 오류가 생성 됩니다.  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```