---
title: 컴파일러 오류 C3279 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a86f3dd637f84901559c4be8443a81425347237
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3279"></a>컴파일러 오류 C3279
cli 네임스페이스에 선언된 클래스 템플릿의 명시적 인스턴스화 및 부분/명시적 특수화는 허용되지 않습니다.  
  
 `cli` 네임스페이스는 Microsoft에 의해 정의되며 의사(pseudo) 템플릿을 포함합니다. Visual C++ 컴파일러는 이 네임스페이스에서 사용자 정의, 부분 및 명시적 특수화와 클래스 템플릿의 명시적 인스턴스화를 허용하지 않습니다.  
  
 다음 샘플에서는 C3279를 생성합니다.  
  
```  
// C3279.cpp  
// compile with: /clr  
namespace cli {  
   template <> ref class array<int> {};   // C3279  
   template <typename T> ref class array<T, 2> {};   // C3279  
}  
```