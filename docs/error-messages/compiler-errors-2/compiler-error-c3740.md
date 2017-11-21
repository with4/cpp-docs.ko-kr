---
title: "컴파일러 오류 C3740 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3740
dev_langs: C++
helpviewer_keywords: C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1466945e3b6647bedccd65e899bb3eb78ac28de1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3740"></a>컴파일러 오류 C3740
서식 파일 원본 또는 이벤트를 받을 수 없습니다.  
  
 템플릿 기반 클래스 또는 구조체를 포함할 수 없습니다 [이벤트](../../cpp/event-handling.md)합니다.  
  
 다음 샘플에서는 C3740 오류가 생성 됩니다.  
  
```  
// C3740.cpp  
template <typename T>   // Delete the template specification  
struct E {  
   __event void f();   // C3740  
};  
  
int main() {  
}  
```