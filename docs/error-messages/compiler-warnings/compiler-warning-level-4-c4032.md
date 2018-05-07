---
title: 컴파일러 경고 (수준 4) C4032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4032
dev_langs:
- C++
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb61588c12378972194305d979ecdd89140ac6f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4032"></a>컴파일러 경고 (수준 4) C4032
형식 매개 변수 'number'의 형식이 다릅니다.  
  
 매개 변수 형식이 기본 확장이 긴 하지만 이전 선언에 형식이 호환 되지 않습니다.  
  
 이것은 ANSI C에서 오류 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) 및 Microsoft 확장명 (/Ze)에서는 경고 합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```