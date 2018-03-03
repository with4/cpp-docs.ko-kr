---
title: "컴파일러 오류 C3769 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea13880843f5ca35b8cdda2218f19e5491be504c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3769"></a>컴파일러 오류 C3769
'type': 중첩 된 클래스에는 바로 바깥쪽 클래스와 동일한 이름을 가질 수 없습니다  
  
 중첩된 클래스 바로 바깥쪽의 클래스와 같은 이름을 사용할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3769 오류가 발생 합니다.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```