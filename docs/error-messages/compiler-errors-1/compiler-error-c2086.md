---
title: 컴파일러 오류 C2086 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f1a21c06adeeda5d9db428e984da51f06addb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2086"></a>컴파일러 오류 C2086
'identifier': 재정의  
  
 식별자가 두 번 이상 정의 하 또는 후속 선언 이전 쿼리와 다릅니다.  
  
 C2086 C# 어셈블리 참조에 대 한 증분 빌드의 결과로 될 수도 있습니다. 이 오류를 해결 하려면 C# 어셈블리를 다시 작성 합니다.  
  
 다음 샘플에서는 C2086 오류가 생성 됩니다.  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```