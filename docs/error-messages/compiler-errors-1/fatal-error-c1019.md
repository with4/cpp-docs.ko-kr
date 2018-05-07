---
title: 심각한 오류 C1019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1019
dev_langs:
- C++
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 119ff2df1554467762c0b960e80ad4c241517628
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1019"></a>심각한 오류 C1019
예기치 않은 #else입니다.  
  
 `#else` 지시문이 `#if`, `#ifdef`또는 `#ifndef` 구문 외부에 표시됩니다. `#else` 는 이러한 구문 중 하나 내에서만 사용합니다.  
  
 다음 샘플에서는 C1019를 생성합니다.  
  
```  
// C1019.cpp  
#else   // C1019  
#endif  
  
int main() {}  
```  
  
 해결 방법:  
  
```  
// C1019b.cpp  
#if 1  
#else  
#endif  
  
int main() {}  
```