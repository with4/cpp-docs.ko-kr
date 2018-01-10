---
title: "컴파일러 오류 C3207 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3207
dev_langs: C++
helpviewer_keywords: C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04aecf7f37d7e631a9dc07c7f029257c274f6538
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3207"></a>컴파일러 오류 C3207
'function': 'arg'에 대한 템플릿 인수가 잘못되었습니다. 클래스 템플릿이 필요합니다.  
  
 템플릿 함수가 템플릿 인수를 사용하도록 정의되어 있습니다. 그러나 템플릿 형식 인수가 전달되었습니다.  
  
 다음 샘플에서는 C3207을 생성합니다.  
  
```  
// C3207.cpp  
template <template <class T> class TT>  
void f(){}  
  
template <class T>  
struct S  
{  
};  
  
void f1()  
{  
   f<S<int> >();   // C3207  
   // try the following line instead  
   // f<S>();  
}  
```