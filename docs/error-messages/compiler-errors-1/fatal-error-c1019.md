---
title: "심각한 오류 C1019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1019
dev_langs:
- C++
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 90d826ded9ebd8fdc2b304900af523b7ffe8b395
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
