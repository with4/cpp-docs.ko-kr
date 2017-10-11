---
title: "컴파일러 오류 C3237 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3237
dev_langs:
- C++
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 21642184acebf358e92802f0a1aad9e2d227110a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3237"></a>컴파일러 오류 C3237
'generic_class': 제네릭 클래스는 사용자 지정 특성이 될 수 없습니다.  
  
 제네릭 클래스는 사용자 정의 특성이 될 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3237을 생성합니다.  
  
```  
// C3237.cpp  
// compile with: /clr /c  
// C3237 expected  
using namespace System;  
  
generic <class T>  
// Delete the following line to resolve.  
[attribute(AttributeTargets::All, AllowMultiple=true)]  
public ref class GR {};  
```
