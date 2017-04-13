---
title: "컴파일러 오류 C3309 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3309
dev_langs:
- C++
helpviewer_keywords:
- C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
caps.latest.revision: 7
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
ms.openlocfilehash: 73ebbcad685faf64034ac58639c2fc63e4d9ad98
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3309"></a>컴파일러 오류 C3309
'macro_name': 모듈 이름은 매크로 또는 키워드일 수 없습니다.  
  
 모듈 특성의 name 속성에 전달하는 값은 확장할 전처리기의 기호일 수 없습니다. 문자열 리터럴이어야 합니다.  
  
 다음 샘플에서는 C3309를 생성합니다.  
  
```  
// C3309.cpp  
#define NAME MyModule  
[module(name="NAME")];   // C3309  
// Try the following line instead  
// [module(name="MyModule")];  
[coclass]  
class MyClass {  
public:  
   void MyFunc();  
};  
  
int main() {  
}  
```
