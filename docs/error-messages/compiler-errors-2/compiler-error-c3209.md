---
title: "컴파일러 오류 C3209 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3209
dev_langs:
- C++
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 99cffcf55850035bc114c5b158ad3fde304234f0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3209"></a>컴파일러 오류 C3209
'class': 제네릭 클래스 또는 관리 되는 WinRTclass 있어야 합니다.  
  
 제네릭 클래스는 관리되는 클래스 또는 Windows 런타임 클래스여야 합니다.  
  
 다음 샘플에서는 C3209를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3209.cpp  
// compile with: /clr  
generic <class T>  
class C {};   // C3209  
  
// OK - ref class can be generic  
generic <class T>  
ref class D {};  
```
