---
title: "컴파일러 오류 C3215 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3215
dev_langs:
- C++
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
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
ms.openlocfilehash: 331de627b05a57d630b83bd20a625e368527631e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3215"></a>컴파일러 오류 C3215
'type1': 제네릭 형식 매개 변수가 이미 'type2'의 제약을 받습니다.  
  
 제약 조건을 두 번 이상 지정했습니다.  
  
 제네릭에 대 한 자세한 내용은 참조 하십시오. [제네릭](../../windows/generics-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3215를 생성합니다.  
  
```  
// C3215.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where T : A,A  
ref class C {};   // C3215  
```  
  
 해결 방법:  
  
```  
// C3215b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```
