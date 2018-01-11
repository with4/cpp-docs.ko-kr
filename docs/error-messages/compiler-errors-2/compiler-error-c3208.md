---
title: "컴파일러 오류 C3208 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3208
dev_langs: C++
helpviewer_keywords: C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5f9346ae786b967ccff4adfe2deddee839c361d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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