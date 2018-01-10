---
title: "컴파일러 오류 C2563 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2563
dev_langs: C++
helpviewer_keywords: C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dfd46b56de9bcdec0d742c488b96b76066478246
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2563"></a>컴파일러 오류 C2563
형식 매개 변수 목록에서 일치 하지 않습니다.  
  
 함수 (또는 함수에 대 한 포인터)의 형식 매개 변수 목록에 다른 함수 (또는 멤버 함수에 대 한 포인터)의 인수와 일치 하지 않습니다. 결과적으로, 함수 또는 포인터의 할당을 만들 수 없습니다.  
  
 다음 샘플에서는 C2563 오류가 생성 됩니다.  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```