---
title: "컴파일러 오류 C3202 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3202
dev_langs:
- C++
helpviewer_keywords:
- C3202
ms.assetid: 23528a0c-5493-4804-9789-cd3c38e49fb9
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 60e0432a40b7aa66762c235223b0f8d48a50bab4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3202"></a>컴파일러 오류 C3202
'arg name' : 템플릿 매개 변수 'parameter'에 대한 기본 인수가 잘못되었습니다. 클래스 템플릿이 필요합니다.  
  
 템플릿 매개 변수에 대해 잘못된 기본 인수를 전달했습니다.  
  
 다음 샘플에서는 C3202를 생성합니다.  
  
```  
// C3202.cpp  
template<typename T>  
class X  
{  
};  
  
class Z  
{  
};  
  
template<template<typename U> class T1 = Z, typename T2> // C3202  
class Y  
{  
};  
```
