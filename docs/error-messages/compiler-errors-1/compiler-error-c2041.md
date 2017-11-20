---
title: "컴파일러 오류 C2041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2041
dev_langs: C++
helpviewer_keywords: C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4102f95b5a48860cba2e9ec79d2d5c22cd1413cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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