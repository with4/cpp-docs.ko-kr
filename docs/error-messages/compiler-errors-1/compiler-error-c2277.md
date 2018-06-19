---
title: 컴파일러 오류 C2277 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2277
dev_langs:
- C++
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7338efab684e9812704673ece8585cd58c850b23
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171733"
---
# <a name="compiler-error-c2277"></a>컴파일러 오류 C2277
'identifier':이 멤버 함수의 주소를 가져올 수 없습니다  
  
 멤버 함수의 주소를 가져올 수 없습니다.  
  
 다음 샘플에서는 C2277 오류가 생성 됩니다.  
  
```  
// C2277.cpp  
class A {  
public:  
   A();  
};  
(*pctor)() = &A::A;   // C2277   
```