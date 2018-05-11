---
title: 컴파일러 오류 C2811 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2811
dev_langs:
- C++
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef9c608f19be28dbbeeca89c5f6672149e0ac4f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2811"></a>컴파일러 오류 C2811
'type1': ref 'type2'에서 상속할 수 없습니다는 ref 클래스 또는 인터페이스 클래스에서 클래스 에서만 상속할 수 있습니다  
  
 관리 되는 클래스에 대 한 관리 되지 않는 클래스를 기본 클래스로 사용 하려고 했습니다.  
  
 다음 샘플에서는 C2811 오류가 생성 됩니다.  
  
```  
// C2811.cpp  
// compile with: /clr /c  
struct S{};  
ref struct T {};  
ref class C : public S {};   // C2811  
ref class D : public T {};   // OK  
```