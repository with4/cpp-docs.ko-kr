---
title: "컴파일러 오류 C3208 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3208
dev_langs:
- C++
helpviewer_keywords:
- C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
caps.latest.revision: 5
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
ms.openlocfilehash: 3258ae0d8a52b00f7ac2f783d0abf5a0da82574d
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3208"></a>컴파일러 오류 C3208
'function': 클래스 템플릿 'class'에 대한 템플릿 매개 변수 목록이 template 템플릿 매개 변수 'parameter'에 대한 템플릿 매개 변수 목록과 일치하지 않습니다.  
  
 template 템플릿 매개 변수의 템플릿 매개 변수 개수가 제공된 클래스 템플릿과 다릅니다.  
  
 다음 샘플에서는 C3208을 생성합니다.  
  
```  
// C3208.cpp  
template <template <class T> class TT >  
int f();  
  
template <class T1, class T2>  
struct S;  
  
template <class T1>  
struct R;  
  
int i = f<S>();   // C3208  
// try the following line instead  
// int i = f<R>();  
```
