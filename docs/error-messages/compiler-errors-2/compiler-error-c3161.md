---
title: "컴파일러 오류 C3161 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4be981b2af166d85a3a83209a901f3e3e51b6246
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3161"></a>컴파일러 오류 C3161
'interface': 중첩 클래스, 구조체, 공용 구조체 또는 인터페이스의 인터페이스 올바르지 않습니다. 클래스, 구조체 또는 공용 구조체에 중첩 인터페이스 올바르지 않습니다.  
  
 [__interface](../../cpp/interface.md) 전역 범위 또는 네임 스페이스 내에 사용할 수 있습니다. 클래스, 구조체 또는 공용 구조체는 인터페이스에 표시할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3161 오류가 발생 합니다.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```
