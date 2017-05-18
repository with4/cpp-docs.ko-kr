---
title: "컴파일러 오류 C2909 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2909
dev_langs:
- C++
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 89bf4cde99d9629a0057106ff14f5641f81dbdde
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2909"></a>컴파일러 오류 C2909
'identifier': 함수 템플릿을 명시적으로 인스턴스화하려면 반환 형식이 있어야 합니다.  
  
 함수 템플릿의 명시적으로 인스턴스화하려면 해당 반환 형식의 명시적 사양이 있어야 합니다. 암시적 반환 형식 사양은 작동하지 않습니다.  
  
 다음 샘플에서는 C2909를 생성합니다.  
  
```  
// C2909.cpp  
// compile with: /c  
template<class T> int f(T);  
template f<int>(int);         // C2909  
template int f<int>(int);   // OK  
```
