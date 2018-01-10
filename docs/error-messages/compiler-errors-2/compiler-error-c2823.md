---
title: "컴파일러 오류 C2823 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2823
dev_langs: C++
helpviewer_keywords: C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84640d17479c27047919016525272ee5a87d178b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2823"></a>컴파일러 오류 C2823  
  
> typedef 템플릿이 잘못 되었습니다.  
  
서식 파일에서 허용 되지 않는 `typedef` 정의 합니다.  
  
## <a name="example"></a>예  
  
다음 샘플에서는 C2823, 경고가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```cpp  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```