---
title: "컴파일러 오류 C3296 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3296
dev_langs:
- C++
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73f6e8260532164e9ea6a4d3f7330ba51043aa82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3296"></a>컴파일러 오류 C3296
'property': 같은 이름의 속성이 이미 있습니다.  
  
 컴파일러가 동일한 이름의 속성을 둘 이상 발견했습니다. 형식의 각 속성에는 고유한 이름이 있어야 합니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)을 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3296을 생성합니다.  
  
```  
// C3296.cpp  
// compile with: /clr /c  
using namespace System;  
  
ref class R {  
public:  
   property int MyProp[int] { int get(int); }  
  
   property String^ MyProp[int] { void set(int, String^); }   // C3296  
};  
```