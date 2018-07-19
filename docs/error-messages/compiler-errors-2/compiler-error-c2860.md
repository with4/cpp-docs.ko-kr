---
title: 컴파일러 오류 C2860 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2860
dev_langs:
- C++
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ced30a3d737cc8fbd8599489600674da423dbfc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245227"
---
# <a name="compiler-error-c2860"></a>컴파일러 오류 C2860
'void', '(void)'를 제외한 인수 형식일 수 없습니다  
  
 형식 `void` 다른 인수를 포함 하는 인수 형식으로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2860 오류가 생성 됩니다.  
  
```  
// C2860.cpp  
// compile with: /c  
void profunc1(void, int i);   // C2860  
void func10(void);   // OK  
```