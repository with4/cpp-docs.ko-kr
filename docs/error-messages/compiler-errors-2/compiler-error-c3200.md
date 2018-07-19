---
title: 컴파일러 오류 C3200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3200
dev_langs:
- C++
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa34ea006b06138290417387bd393589b630aa4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251309"
---
# <a name="compiler-error-c3200"></a>컴파일러 오류 C3200
'template': 템플릿 매개 변수 'parameter'에 대 한 잘못 된 템플릿 인수. 클래스 템플릿이 필요  
  
 클래스 템플릿을에 잘못 된 인수를 전달 합니다. 클래스 템플릿에서 매개 변수로 템플릿이 필요합니다. 다음 예제에서는 호출 `Y<int, int> aY` C3200를 생성 합니다. 첫 번째 매개 변수 수와 같은 해야 `Y<X, int> aY`합니다.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```