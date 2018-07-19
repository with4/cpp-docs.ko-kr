---
title: 컴파일러 오류 C2345 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2345
dev_langs:
- C++
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 528afe4ba6c9dd0b22b4664de706ba4370497c88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196129"
---
# <a name="compiler-error-c2345"></a>컴파일러 오류 C2345
align(value): 맞춤 값이 잘못되었습니다.  
  
 [align](../../cpp/align-cpp.md) 키워드에 허용 범위 외부의 값을 전달했습니다.  
  
 다음 코드에서는 C2345를 생성합니다.  
  
```  
// C2345.cpp  
// compile with: /c  
__declspec(align(0)) int a;   // C2345  
__declspec(align(1)) int a;   // OK  
```