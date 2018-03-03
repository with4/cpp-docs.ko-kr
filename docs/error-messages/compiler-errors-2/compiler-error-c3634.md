---
title: "컴파일러 오류 C3634 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3634
dev_langs:
- C++
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8bbd6e763bd11dea73acd539ed7a536989d1a5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3634"></a>컴파일러 오류 C3634
'function': 관리 되는 또는 WinRTclass의 추상 메서드를 정의할 수 없습니다  
  
 WinRT 또는 관리되는 클래스에서 추상 메서드를 선언할 수 있지만 정의할 수는 없습니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C3634 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3634.cpp  
// compile with: /clr  
ref class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```  
