---
title: "컴파일러 오류 C2503 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2503
dev_langs: C++
helpviewer_keywords: C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a5a005e07f885fa9113f7810e15ba8bb6a19c80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2503"></a>컴파일러 오류 C2503
'class': 기본 클래스에는 크기가 0 인 배열을 포함할 수 없습니다  
  
 기본 클래스 또는 구조체에 크기가 0 인 배열이 포함 되어 있습니다. 클래스에서 배열에 요소가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2503 오류가 생성 됩니다.  
  
```  
// C2503.cpp  
// compile with: /c  
class A {  
   public:  
   int array [];  
};  
  
class B : A {};    // C2503  
  
class C {  
public:  
   int array [10];  
};  
  
class D : C {};  
```