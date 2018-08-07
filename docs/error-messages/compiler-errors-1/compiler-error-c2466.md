---
title: 컴파일러 오류 C2466 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e55e5c130b0a0454577a7155b704a18933b86198
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33224310"
---
# <a name="compiler-error-c2466"></a>컴파일러 오류 C2466
상수 크기 0의 배열을 할당할 수 없습니다.  
  
 배열을 할당 하거나 크기가 0 사용 하 여 선언 합니다. 배열 크기에 대 한 상수 식에는 0 보다 큰 정수 여야 합니다. 배열 첨자가 0 선언은 클래스, 구조체 또는 공용 구조체 멤버에 대해서만 사용할 Microsoft 확장 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 다음 샘플에서는 C2466 오류가 생성 됩니다.  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```