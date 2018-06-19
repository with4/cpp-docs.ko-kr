---
title: 컴파일러 경고 (수준 4) C4212 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4212
dev_langs:
- C++
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb70cf045a1cc563e4eb009ed00ffe82be812b0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292005"
---
# <a name="compiler-warning-level-4-c4212"></a>컴파일러 경고(수준 4) C4212
비표준 확장이 사용 됨: 줄임표를 사용 하는 함수 선언  
  
 함수 프로토타입에 인수의 변수 수 있습니다. 함수 정의 그렇지 않습니다.  
  
 다음 샘플에서는 C4212 오류가 생성 됩니다.  
  
```  
// C4212.c  
// compile with: /W4 /Ze /c  
void f(int , ...);  
void f(int i, int j) {}  
```