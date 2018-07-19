---
title: 컴파일러 경고 (수준 2) C4308 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4308
dev_langs:
- C++
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3daff15f8e6eee179f04fd466f3595af1154e035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290012"
---
# <a name="compiler-warning-level-2-c4308"></a>컴파일러 경고(수준 2) C4308
음의 정수 상수가 부호 없는 형식으로 변환  
  
 식 부호 없는 형식에는 음의 정수 상수를 변환합니다. 식의 결과 의미가입니다.  
  
## <a name="example"></a>예제  
  
```  
// C4308.cpp  
// compile with: /W2  
unsigned int u = (-5 + 3U);   // C4308  
  
int main()  
{  
}  
```