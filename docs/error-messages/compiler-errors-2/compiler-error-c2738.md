---
title: 컴파일러 오류 C2738 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2738
dev_langs:
- C++
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f056d8f38c36011e2b9025283e46164fe53061fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236731"
---
# <a name="compiler-error-c2738"></a>컴파일러 오류 C2738
'declaration': 모호 하거나 'type'의 구성원이 아닙니다  
  
 함수를 잘못 선언 되었습니다.  
  
 다음 샘플에서는 C2738 오류가 생성 됩니다.  
  
```  
// C2738.cpp  
struct A {  
   template <class T> operator T*();  
   // template <class T> operator T();  
};  
  
template <>  
A::operator int() {   // C2738  
  
// try the following line instead  
// A::operator int*() {  
  
// or use the commented member declaration  
  
   return 0;  
}  
```