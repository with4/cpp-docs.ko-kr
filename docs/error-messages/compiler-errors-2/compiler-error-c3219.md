---
title: 컴파일러 오류 C3219 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3219
dev_langs:
- C++
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16341412ae5028753b2a542b45da4ea2b549c29e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3219"></a>컴파일러 오류 C3219
'param': 제네릭 매개 변수는 여러 개의 비인터페이스('class')에 의해 제약을 받을 수 없습니다.  
  
 제네릭 매개 변수를 둘 이상의 관리되는 클래스로 제한할 수 없습니다.  
  
 다음 샘플에서는 C3219를 생성합니다.  
  
```  
// C3219.cpp  
// compile with: /clr  
ref class A {};  
ref class B {};  
  
generic <class T>  
where T : A, B  
ref class E {};   // C3219  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3219b.cpp  
// compile with: /clr /c  
ref class A {};  
  
interface struct C {};  
  
generic <class T>  
where T : A  
ref class E {};  
```