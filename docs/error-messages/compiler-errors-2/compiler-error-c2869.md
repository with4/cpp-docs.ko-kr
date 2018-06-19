---
title: 컴파일러 오류 C2869 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2869
dev_langs:
- C++
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9aa6092347b224abf02e0d6fac394146094e576
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246254"
---
# <a name="compiler-error-c2869"></a>컴파일러 오류 C2869
'name': 이미 네임 스페이스로 정의  
  
 네임 스페이스도 이미 사용 되는 이름을 다시 사용할 수 없습니다.  
  
 다음 샘플에서는 C2869 오류가 생성 됩니다.  
  
```  
// C2869.cpp  
// compile with: /c  
namespace A { int i; };  
  
class A {};   // C2869, A is already used  
```