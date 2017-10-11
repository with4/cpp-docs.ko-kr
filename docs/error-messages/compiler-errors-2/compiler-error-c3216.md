---
title: "컴파일러 오류 C3216 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3216
dev_langs:
- C++
helpviewer_keywords:
- C3216
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6f188191298c83951ccced6ed466303e2ada9ebc
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3216"></a>컴파일러 오류 C3216
제약 조건은 'type'이 아니라 제네릭 매개 변수여야 합니다.  
  
 제약 조건 형식이 잘못되었습니다.  
  
 다음 샘플에서는 C3216을 생성합니다.  
  
```  
// C3216.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where F : A   // C3216  
// Try the following line instead:  
// where T : A    // C3216  
ref class C {};  
```  
  
 다음 예제에서는 가능한 해결 방법을 설명합니다.  
  
```  
// C3216b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```
