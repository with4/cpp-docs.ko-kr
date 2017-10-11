---
title: "컴파일러 오류 C3142 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3142
dev_langs:
- C++
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 56322d31f7a90612957ab82cd238b83e1789028a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3142"></a>컴파일러 오류 C3142
'property_name': 속성의 주소를 가져올 수 없습니다  
  
 속성의 주소를 개발자에 게 사용할 수 없는 경우  
  
 다음 샘플에서는 C3142 오류가 생성 됩니다.  
  
```  
// C3142_2.cpp  
// compile with: /clr  
using namespace System;  
ref class CSize {  
private:  
   property int Size {  
      int get();  
   }  
};  
  
int main() {  
    &CSize::Size; // C3142  
}  
```  

