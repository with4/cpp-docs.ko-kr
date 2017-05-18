---
title: "컴파일러 오류 C3181 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 4229a9d9811bad46035451c5d64b7ed06da476d2
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3181"></a>컴파일러 오류 C3181
'type': 연산자에 대 한 잘못 된 피연산자  
  
에 잘못 된 매개 변수가 전달 된는 [typeid](../../windows/typeid-cpp-component-extensions.md) 연산자입니다. 매개 변수는 관리 되는 형식 이어야 합니다.  
  
컴파일러는 공용 언어 런타임에서 형식에 매핑되는 네이티브 형식에 대 한 별칭을 사용 하는 참고 합니다.  
  
다음 샘플에서는 C3181 오류가 생성 됩니다.  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  

