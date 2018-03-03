---
title: "컴파일러 오류 C2161 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2161
dev_langs:
- C++
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11298c107aa927e62e4bc84f2d709c6f46c54c98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2161"></a>컴파일러 오류 C2161
매크로 정의 끝에 '##'이 올 수 없습니다.  
  
 매크로 정의가 토큰 붙여넣기 연산자(##)로 종료되었습니다.  
  
 다음 샘플에서는 C2161 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2161.cpp  
// compile with: /c  
#define mac(a,b) a   // OK  
#define mac(a,b) a##   // C2161  
```