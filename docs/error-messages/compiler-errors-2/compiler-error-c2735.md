---
title: "컴파일러 오류 C2735 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2735
dev_langs: C++
helpviewer_keywords: C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1008ef6178a4220bac718e08ba31a36d5db3242f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2735"></a>컴파일러 오류 C2735
형식 매개 변수 형식 지정자에는 'keyword' 키워드를 사용할 수 없습니다.  
  
 키워드가이 컨텍스트에서 올바르지 않습니다.  
  
 다음 샘플에서는 C2735 오류가 생성 됩니다.  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```