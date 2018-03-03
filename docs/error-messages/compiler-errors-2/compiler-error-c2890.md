---
title: "컴파일러 오류 C2890 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2890
dev_langs:
- C++
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 829ed6646578e35a2887d2f18de9c7a89b22b3ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2890"></a>컴파일러 오류 C2890
'class': ref 클래스는 하나의 비 인터페이스 기본 클래스를 하나만 사용할 수 있습니다  
  
 참조 클래스 단 하나의 기본 클래스를 하나만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2890 오류가 생성 됩니다.  
  
```  
// C2890.cpp  
// compile with: /clr /c  
ref class A {};  
ref class B {};  
ref class C : public A, public B {};   // C2890  
ref class D : public A {};   // OK  
```  
