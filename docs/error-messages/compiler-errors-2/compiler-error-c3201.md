---
title: "컴파일러 오류 C3201 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3201
dev_langs:
- C++
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c398d3251c63a763af0fdf965e4c7f2e8c5bb3c4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3201"></a>컴파일러 오류 C3201
클래스 템플릿 'template'에 대한 템플릿 매개 변수 목록이 템플릿 매개 변수 'template'에 대한 템플릿 매개 변수 목록과 일치하지 않습니다.  
  
 템플릿 매개 변수를 사용하지 않는 클래스 템플릿에 클래스 템플릿을 인수로 전달했거나 기본 템플릿 인수에 대해 일치하지 않는 개수의 템플릿 인수를 전달했습니다.  
  
```  
// C3201.cpp  
template<typename T1, typename T2>  
class X1  
{  
};  
  
template<template<typename T> class U = X1>   // C3201  
class X2  
{  
};  
  
template<template<typename T, typename V> class U = X1>   // OK  
class X3  
{  
};  
```
