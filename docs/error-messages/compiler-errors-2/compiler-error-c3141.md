---
title: "컴파일러 오류 C3141 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3141
dev_langs:
- C++
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 00266db4fde48b175b9374ca31a89b15ca13ced2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
