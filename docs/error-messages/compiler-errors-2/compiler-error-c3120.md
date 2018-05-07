---
title: 컴파일러 오류 C3120 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3120
dev_langs:
- C++
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e27d066d7d0a3c34adbbfe10cc7b4e39e563830
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3120"></a>컴파일러 오류 C3120
'method_name': 인터페이스 메서드는 가변 인수 목록을 사용할 수 없습니다  
  
 인터페이스 메서드는 가변 인수 목록을 사용할 수 없습니다. 예를 들어 다음 인터페이스 정의 C3120에서는 생성 됩니다.  
  
```  
// C3120.cpp  
__interface A {  
int X(int i, ...);    // C3120  
};  
  
int main(void) { return(0); }  
```