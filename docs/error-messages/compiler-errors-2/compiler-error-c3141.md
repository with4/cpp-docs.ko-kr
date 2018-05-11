---
title: 컴파일러 오류 C3141 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3141
dev_langs:
- C++
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a394fb06fce8f482f42271052a3cf97b3711eaf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3141"></a>컴파일러 오류 C3141
'interface_name': 인터페이스에는 공용 상속만 지원  
  
 정의 된 인터페이스는 [인터페이스 (또는 __interface)](../../cpp/interface.md) 키워드에는 공용 상속만 지원 합니다.  
  
 다음 샘플에서는 C3141 오류가 생성 됩니다.  
  
```  
// C3141.cpp  
__interface IBase {};  
__interface IDerived1 : protected IBase {};  // C3141  
__interface IDerived2 : private IBase {};    // C3141  
```