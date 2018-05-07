---
title: 컴파일러 오류 C2947 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1af4e6a5a27c13d69351eaf0cddfafe11ba5f22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2947"></a>컴파일러 오류 C2947
construct을(를) 끝내려면 '>' 기호가 있어야 하는데 'syntax'이(가) 있습니다.  
  
 제네릭 또는 템플릿 인수 목록은 올바르게 종료 되지 않을 수 있습니다.  
  
 C2947 구문 오류로 인해 발생할 수도 있습니다.  
  
 다음 샘플에서는 C2947 오류가 생성 됩니다.  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```