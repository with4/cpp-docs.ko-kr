---
title: 컴파일러 경고 (수준 4) C4429 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4429
dev_langs:
- C++
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00d4812fb1eefdd4364376288f063a6bf8b5dddf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4429"></a>컴파일러 경고(수준 4) C4429
가능한 불완전 하거나 형식이 잘못 된 유니버설 문자 이름  
  
 컴파일러가 잘못 된 형식의 유니버설 문자 이름 수 있는 문자 시퀀스를 발견 했습니다. 유니버설 문자 이름은 `\u` 4 개의 16 진수 숫자, 또는 `\U` 8 개의 16 진수 숫자가 차례로 표시 합니다.  
  
 다음 샘플에서는 C4429 오류가 생성 됩니다.  
  
```  
// C4429.cpp  
// compile with: /W4 /WX  
int \ug0e4 = 0;   // C4429  
// Try the following line instead:  
// int \u00e4 = 0;   // OK, a well-formed universal character name.  
```