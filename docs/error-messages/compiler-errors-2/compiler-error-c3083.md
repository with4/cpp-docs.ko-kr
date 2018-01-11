---
title: "컴파일러 오류 C3083 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3083
dev_langs: C++
helpviewer_keywords: C3083
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a24a362ff1eb20e6122a6a4d85afa0334b708fa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3083"></a>컴파일러 오류 C3083
'function': 왼쪽의 기호는 ':: ' 형식 이어야 합니다  
  
 함수를 잘못 호출 했습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3083 오류가 발생 합니다.  
  
```  
// C3083.cpp  
// compile with: /c  
struct N {  
   ~N();  
};  
  
struct N1 {  
   ~N1();  
};  
  
N::N::~N() {}   // C3083  
N1::~N1() {}   // OK  
```