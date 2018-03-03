---
title: "컴파일러 오류 C2041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f498e2858dad5bc42af6bcfbf4f056d2c530220f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2041"></a>컴파일러 오류 C2041
'character' 기본 'number'에 대 한 잘못 된 자릿수  
  
 지정 된 문자 (예: 8 진수 또는 16 진수) 자료에 유효한 숫자가 아닌 경우  
  
 다음 샘플에서는 C2041 오류가 생성 됩니다.  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 해결 방법:  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```