---
title: 컴파일러 오류 C2932 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2932
dev_langs:
- C++
helpviewer_keywords:
- C2932
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5884ca64c51fec699b870f909f23c2e2148092be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2932"></a>컴파일러 오류 C2932
'class': type-class-id가 'identifier'의 데이터 멤버로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 데이터 멤버로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2932를 생성합니다.  
  
```  
// C2932.cpp  
// compile with: /c  
template<class T>   
struct TC {};   
  
struct MyStruct {  
   int TC<int>;   // C2932  
   int TC;   // OK  
};  
```  
  
 C2932는 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2932b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
  
struct MyStruct {  
   int GC<int>;   // C2932  
   int GC;   // OK  
};  
```