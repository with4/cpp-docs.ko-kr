---
title: 컴파일러 오류 C2989 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2989
dev_langs:
- C++
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7831f9255485ede8db9d853ca5fe89dc9a4c2a65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245850"
---
# <a name="compiler-error-c2989"></a>컴파일러 오류 C2989
'class': 비 클래스 형식으로 이미 선언 된 클래스 형식  
  
 제네릭 클래스 또는 템플릿 또는 제네릭이 아닌 클래스를 재정의합니다. 헤더 파일의 충돌을 확인 합니다.  
  
 클래스 템플릿 부분 특수화를 사용 하는 경우 기술 자료 문서를 Q240866를 참조 하십시오.  
  
 다음 샘플에서는 C2989 오류가 생성 됩니다.  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 C2989는 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```