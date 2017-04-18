---
title: "컴파일러 오류 C3233 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3233
dev_langs:
- C++
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c92be4ab9e6cb00c4238d753eefe0cadb3bdf607
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3233"></a>컴파일러 오류 C3233
'type': 제네릭 형식 매개 변수에 이미 제약 조건이 적용되었습니다.  
  
 제네릭 매개 변수를 둘 이상의 `where` 절에 포함할 수 없습니다.  
  
 다음 샘플에서는 C3233을 생성합니다.  
  
```  
// C3233.cpp  
// compile with: /clr /LD  
  
interface struct C {};  
interface struct D {};  
  
generic <class T>  
where T : C  
where T : D  
ref class E {};   // C3233  
```
