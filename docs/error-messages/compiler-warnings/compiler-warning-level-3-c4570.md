---
title: "컴파일러 경고 (수준 3) C4570 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4570
dev_langs: C++
helpviewer_keywords: C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ecd1794de0ad36c5116d5db9f051ed9ddc9cf12e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4570"></a>컴파일러 경고(수준 3) C4570
'type': 명시적으로 선언 되지 추상 않았지만 추상 함수를가지고  
  
 포함 하는 형식을 [추상](../../windows/abstract-cpp-component-extensions.md) 함수 자체 수 추상으로 표시 되어야 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4570 오류가 발생 합니다.  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```