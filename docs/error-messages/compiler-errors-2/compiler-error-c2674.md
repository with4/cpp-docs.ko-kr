---
title: "컴파일러 오류 C2674 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2674
dev_langs:
- C++
helpviewer_keywords:
- C2674
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e95a91ac0610661d739ff7f2a4964ac45725b74e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2674"></a>컴파일러 오류 C2674
제네릭 선언은이 컨텍스트에서 사용할 수 없습니다.  
  
 제네릭 잘못 선언 되었습니다. 자세한 내용은 [제네릭](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2674 오류가 발생 합니다.  
  
```  
// C2674.cpp  
// compile with: /clr /c  
void F(generic <class T> ref class R1);   // C2674  
generic <class T> ref class R2 {};   // OK  
```