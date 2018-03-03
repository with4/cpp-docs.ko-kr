---
title: "컴파일러 오류 C2913 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2913
dev_langs:
- C++
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9485e0bb8df2ae23a571f2546823e6b6742ffa84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2913"></a>컴파일러 오류 C2913
명시적 특수화. 'declaration'는 클래스 템플릿의 특수화  
  
 템플릿이 아닌 클래스를 특수화할 수 없습니다.  
  
 다음 샘플에서는 C2913 오류가 생성 됩니다.  
  
```  
// C2913.cpp  
// compile with: /c  
class X{};  
template <class T> class Y{};  
  
template<> class X<int> {};   // C2913  
template<> class Y<int> {};  
```