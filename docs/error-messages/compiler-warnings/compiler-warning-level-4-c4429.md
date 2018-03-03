---
title: "컴파일러 경고 (수준 4) C4429 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4429
dev_langs:
- C++
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58b2a23b8abb3ab385f8c8a285ad1178299fa52d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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