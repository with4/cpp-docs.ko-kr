---
title: "컴파일러 오류 C3219 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3219
dev_langs:
- C++
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8a320342cdd7d912809ca8b9a29ce99740f1d7f6
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3219"></a>컴파일러 오류 C3219
'param': 제네릭 매개 변수는 여러 개의 비인터페이스('class')에 의해 제약을 받을 수 없습니다.  
  
 제네릭 매개 변수를 둘 이상의 관리되는 클래스로 제한할 수 없습니다.  
  
 다음 샘플에서는 C3219를 생성합니다.  
  
```  
// C3219.cpp  
// compile with: /clr  
ref class A {};  
ref class B {};  
  
generic <class T>  
where T : A, B  
ref class E {};   // C3219  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3219b.cpp  
// compile with: /clr /c  
ref class A {};  
  
interface struct C {};  
  
generic <class T>  
where T : A  
ref class E {};  
```
