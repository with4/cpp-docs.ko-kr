---
title: "컴파일러 오류 C2877 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2877
dev_langs:
- C++
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9549b591341aa8c1922db3ab98029a42de162f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2877"></a>컴파일러 오류 C2877
'symbol'를 'class'에서 액세스할 수 없는 경우  
  
 기본 클래스에서 파생 된 모든 멤버는 파생된 클래스에서 액세스할 수 있어야 합니다.  
  
 다음 샘플에서는 C2877 오류가 생성 됩니다.  
  
```  
// C2877.cpp  
// compile with: /c  
class A {  
private:  
   int a;  
};  
  
class B : public A {  
   using A::a;   // C2877  
};  
```