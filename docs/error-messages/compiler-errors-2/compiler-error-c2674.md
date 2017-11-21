---
title: "컴파일러 오류 C2674 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2674
dev_langs: C++
helpviewer_keywords: C2674
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a71216ee0c9b9bb824e9518691bc71730bb7465
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2674"></a>컴파일러 오류 C2674
제네릭 선언은이 컨텍스트에서 사용할 수 없습니다.  
  
 제네릭 잘못 선언 되었습니다. 자세한 내용은 [제네릭](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2674 오류가 발생 합니다.  
  
```  
// C2674.cpp  
// compile with: /clr /c  
void F(generic <class T> ref class R1);   // C2674  
generic <class T> ref class R2 {};   // OK  
```