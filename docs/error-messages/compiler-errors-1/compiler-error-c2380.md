---
title: 컴파일러 오류 C2380 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2380
dev_langs:
- C++
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa2d0fc361f1cf5ba5355ca11ce86279ebd3575f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195635"
---
# <a name="compiler-error-c2380"></a>컴파일러 오류 C2380
형식 앞에 'identifier' (생성자 반환 형식 또는 현재 클래스 이름을 잘못 재정의 했습니다.)  
  
 생성자는 값을 반환 하거나 클래스 이름을 재정의 합니다.  
  
 다음 샘플에서는 C2326을 생성합니다.  
  
```  
// C2380.cpp  
// compile with: /c  
class C {  
public:  
   int C();   // C2380, specifies an int return  
   int C;   // C2380, redefinition of i  
   C();   // OK  
};  
```