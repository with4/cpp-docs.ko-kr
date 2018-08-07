---
title: 컴파일러 오류 C3213 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3213
dev_langs:
- C++
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbfdbb3554aad858cf412ace7709bbf63b3ae311
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246006"
---
# <a name="compiler-error-c3213"></a>컴파일러 오류 C3213
기본 클래스 'base_type'이 'derived_type'보다 액세스하기 어렵습니다.  
  
 어셈블리에서 볼 수 있는 형식은 공개적으로 볼 수 있는 기본 클래스를 사용해야 합니다.  
  
 다음 샘플에서는 C3213을 생성합니다.  
  
```  
// C3213.cpp  
// compile with: /clr  
private ref struct privateG {  
public:  
   int i;  
};  
  
public ref struct publicG {  
public:  
   int i;  
};  
  
public ref struct V : public privateG {   // C3213  
public:  
   int j;  
};  
  
public ref struct W: public publicG {   // OK  
public:  
   int j;  
};  
```