---
title: "컴파일러 오류 C2287 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2287
dev_langs: C++
helpviewer_keywords: C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed8537c7da77da7e5401448e8a6d579cfb4ebe07
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2287"></a>컴파일러 오류 C2287
'class': 상속 표현: 'representation1' 필수 'representation2' 보다 덜 일반적은  
  
 클래스는 필요한 것 보다 간단한 방식으로 선언 됩니다.  
  
 다음 샘플에서는 C2287 오류가 생성 됩니다.  
  
```  
// C2287.cpp  
// compile with: /vmg /c  
class __single_inheritance X;  
class __single_inheritance Y;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2287  X uses multiple inheritance  
struct Y : A { };  // OK  
```