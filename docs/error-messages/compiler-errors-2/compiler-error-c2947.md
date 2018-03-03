---
title: "컴파일러 오류 C2947 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79083bc2713a21de24008a58ebb02ef15265cf39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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