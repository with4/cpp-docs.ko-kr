---
title: 컴파일러 오류 C2507 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82bd4fb028712093a44ada4ae58e97c2fbcf7eed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230537"
---
# <a name="compiler-error-c2507"></a>컴파일러 오류 C2507
'identifier': 기본 클래스에 가상 한정자가 너무 많은  
  
 클래스 또는 구조체로 선언 됨 `virtual` 두 번 이상. 하나의 `virtual` 한정자 목록에 기본 클래스의 각 클래스에 대해 표시할 수 있습니다.  
  
 다음 샘플에서는 C2507 오류가 생성 됩니다.  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```