---
title: 컴파일러 오류 C2530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b226ef5ca0e839c745e13d4118264a69ca408db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229404"
---
# <a name="compiler-error-c2530"></a>컴파일러 오류 C2530
'identifier': 참조를 초기화 합니다  
  
 초기화 해야 대 한 참조를 선언할 때 이미 선언 되지 않은:  
  
-   키워드와 함께 [extern](../../cpp/using-extern-to-specify-linkage.md)합니다.  
  
-   클래스, 구조체 또는 공용 구조체의 멤버로 (및 생성자에서 초기화).  
  
-   매개 변수로 함수 선언 또는 정의 합니다.  
  
-   으로 함수의 반환 형식입니다.  
  
 다음 샘플에서는 C2530 오류가 생성 됩니다.  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```