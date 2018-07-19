---
title: 컴파일러 오류 C2894 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2894
dev_langs:
- C++
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92c412aa753d4440a25f8123b4b25e40360b7a3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243321"
---
# <a name="compiler-error-c2894"></a>컴파일러 오류 C2894
서식 파일에는 'C' 링크가를 선언할 수 없습니다.  
  
 이 오류를 내에 정의 된 템플릿을 원인일 수 있습니다는 `extern` "C" 블록입니다.  
  
 다음 샘플에서는 C2894 오류가 생성 됩니다.  
  
```  
// C2894.cpp  
extern "C" {  
   template<class T> class stack {};   // C2894 fail  
  
   template<class T> void f(const T &aT) {}   // C2894  
}  
```  
  
 다음 샘플에서는 C2894 오류가 생성 됩니다.  
  
```  
// C2894b.cpp  
// compile with: /c  
extern "C" template<class T> void f(const T &aT) {}   // C2894  
  
template<class T> void f2(const T &aT) {}   // OK  
```