---
title: 컴파일러 오류 C2632 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3bc07c404a1f4d667045fdfea24009e7d20ad69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2632"></a>컴파일러 오류 C2632
'type1' 뒤에 'type2'은 사용할 수 없습니다.  
  
 이 오류는 두 형식 지정자 사이의 코드 누락 된 경우 발생할 수 있습니다.  
  
 다음 샘플에서는 C2632 오류가 생성 됩니다.  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 이 오류는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 수 있습니다. `bool` 이제는 적절 한 형식이입니다. 이전 버전에서는 `bool` typedef와 였으며 해당 이름의 식별자를 만들 수 있습니다.  
  
 다음 샘플에서는 C2632 오류가 생성 됩니다.  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 이 오류를 해결 하는 코드는 Visual Studio.NET 2003와 Visual Studio.NET 버전의 Visual c + +에서 유효 하려면 식별자를 이름을 바꿉니다.