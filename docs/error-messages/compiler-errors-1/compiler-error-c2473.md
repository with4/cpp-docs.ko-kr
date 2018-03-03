---
title: "컴파일러 오류 C2473 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2473
dev_langs:
- C++
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da31fbedf94691a3d9b379c8794ea25f1e16de7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2473"></a>컴파일러 오류 C2473
'identifier': 함수 정의로 보이지만 매개 변수 목록이 없습니다.  
  
 컴파일러가 매개 변수 목록 없이 함수처럼 보이는 항목을 발견했습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2473을 생성합니다.  
  
```  
// C2473.cpp  
// compile with: /clr /c  
class A {  
   int i {}   // C2473  
};  
  
class B {  
   int i() {}   // OK  
};  
```