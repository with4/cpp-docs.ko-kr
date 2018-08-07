---
title: 컴파일러 오류 C3118 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3118
dev_langs:
- C++
helpviewer_keywords:
- C3118
ms.assetid: 40fbe681-8868-4cb2-a2b2-4db4449319a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ecc3dc79cd52631f3dba5c204cabc02e7932bc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244458"
---
# <a name="compiler-error-c3118"></a>컴파일러 오류 C3118
'interface': 인터페이스가 가상 상속을 지원 하지 않습니다  
  
 사실상 인터페이스에서 상속 하려고 했습니다. 예를 들어 개체에 적용된  
  
```  
// C3118.cpp  
__interface I1 {  
};  
  
__interface I2 : virtual I1 {   // C3118  
};  
```  
  
 이 오류를 생성합니다.