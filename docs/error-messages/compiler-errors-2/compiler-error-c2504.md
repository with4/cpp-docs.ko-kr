---
title: "컴파일러 오류 C2504 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0463c762cec98f60b0e8a3811f1f5c9b7e2cdea7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2504"></a>컴파일러 오류 C2504
'class': 기본 정의 되지 않은 클래스  
  
 기본 클래스 선언 되었지만 정의 되지 않았습니다.  가능한 원인:  
  
1.  포함 파일이 없습니다.  
  
2.  기본 클래스 외부로 선언 되지 [extern](../../cpp/using-extern-to-specify-linkage.md)합니다.  
  
 다음 샘플에서는 C2504 오류가 생성 됩니다.  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 그래  
  
```  
class C{};  
class D : public C {};  
```
