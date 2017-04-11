---
title: "컴파일러 경고 (수준 3) C4357 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4357
dev_langs:
- C++
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: dd055c5798b71fb68eec23d00b23a5682230b988
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-warning-level-3-c4357"></a>컴파일러 경고(수준 3) C4357
매개 변수 배열 인수에 대 한 형식 인수 목록에 대리자 'del' 'function'를 생성 하는 경우 무시 됩니다.  
  
 `ParamArray` 특성을 무시 하 고 `function` 가변 인수를 갖는 호출할 수 없습니다.  
  
 다음 샘플에서는 C4357 오류가 생성 됩니다.  
  
```  
// C4357.cpp  
// compile with: /clr /W3 /c  
using namespace System;  
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357  
  
public delegate void g(int i, array<Object^>^ varargs);   // OK  
```
