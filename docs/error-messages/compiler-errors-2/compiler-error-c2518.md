---
title: 컴파일러 오류 C2518 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2518
dev_langs:
- C++
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1e44a99ad49945e441e1560f296dc66568ae3f3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228075"
---
# <a name="compiler-error-c2518"></a>컴파일러 오류 C2518
'keyword' 기본 클래스 목록;에 잘못 된 키워드 무시  
  
 키워드 `class` 및 `struct` 기본 클래스 목록에 표시 되지 않도록 합니다.  
  
 다음 샘플에서는 C2518 오류가 생성 됩니다.  
  
```  
// C2518.cpp  
// compile with: /c  
class B {};  
class C : public class B {};   // C2518  
class D: public B {};   // OK  
```