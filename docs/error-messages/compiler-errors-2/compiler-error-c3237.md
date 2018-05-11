---
title: 컴파일러 오류 C3237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3237
dev_langs:
- C++
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9e43fc9ecf79443cfbf8147ff5b3c227eda9404
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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