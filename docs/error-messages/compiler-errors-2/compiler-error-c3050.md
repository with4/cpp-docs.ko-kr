---
title: 컴파일러 오류 C3050 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3050
dev_langs:
- C++
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a4c5220cbfc897f2952d366d9ce09bfb8d85dc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243661"
---
# <a name="compiler-error-c3050"></a>컴파일러 오류 C3050
'type1': ref 클래스는 'type1'에서 상속될 수 없습니다.  
  
 `System::ValueType` 이 참조 형식에 대한 기본 클래스가 될 수 없습니다.  
  
 다음 샘플에서는 C3050을 생성합니다.  
  
```  
// C3050.cpp  
// compile with: /clr /LD  
ref struct X : System::ValueType {};   // C3050  
ref struct Y {};   // OK  
```