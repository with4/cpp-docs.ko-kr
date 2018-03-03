---
title: "컴파일러 오류 C3118 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3118
dev_langs:
- C++
helpviewer_keywords:
- C3118
ms.assetid: 40fbe681-8868-4cb2-a2b2-4db4449319a7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfa2c70051afa27e65934c684f3ac30d89c6b344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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