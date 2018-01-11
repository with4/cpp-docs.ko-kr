---
title: "컴파일러 오류 C2768 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2768
dev_langs: C++
helpviewer_keywords: C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42f4c23f36669ae2dd3284d8902f6ba017617201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2768"></a>컴파일러 오류 C2768
'function': 명시적 템플릿 인수를 잘못 사용 했습니다.  
  
 컴파일러는 함수 정의 함수 템플릿의 명시적 특수화 했었다면 또는 함수 정의 된 새 함수에 대 한 있어야 할 경우를 확인할 수 없습니다.  
  
 이 오류는 향상 된 컴파일러 규칙의 일부로 Visual Studio.NET 2003에서 도입 되었습니다.  
  
 다음 샘플에서는 C2768 오류가 생성 됩니다.  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```