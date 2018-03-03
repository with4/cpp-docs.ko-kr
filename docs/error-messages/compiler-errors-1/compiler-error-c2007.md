---
title: "컴파일러 오류 C2007 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2007
dev_langs:
- C++
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aca1bc7436905dd7247ad797f47a5b44c8e52993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2007"></a>컴파일러 오류 C2007
\#구문 정의  
  
 뒤에 식별자 없이 표시 됩니다는 `#define`합니다. 이 오류를 해결 하려면 식별자를 사용 합니다.  
  
 다음 샘플에서는 C2007 오류가 생성 됩니다.  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 해결 방법:  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```