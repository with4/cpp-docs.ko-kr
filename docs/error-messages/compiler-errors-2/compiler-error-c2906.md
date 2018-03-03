---
title: "컴파일러 오류 C2906 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2906
dev_langs:
- C++
helpviewer_keywords:
- C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa79e97d21ffff7dd54ff59a18452994999aa4e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2906"></a>컴파일러 오류 C2906
'specialization' : 명시적 특수화에는 'template <>'가 필요합니다.  
  
 템플릿의 명시적 특수화에 대 한 새 구문을 사용 해야 합니다.  
  
 다음 샘플에서는 C2906 오류가 생성 됩니다.  
  
```  
// C2906.cpp  
// compile with: /c  
template<class T> class X{};   // primary template  
class X<int> { }   // C2906  
template<> class X<int> { };   // new syntax  
```