---
title: 컴파일러 오류 C3246 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb7feedafc4c965912bcb8ee022601e52d0c0f3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253254"
---
# <a name="compiler-error-c3246"></a>컴파일러 오류 C3246
'class': 'sealed'로 선언했으므로 'type'에서 상속할 수 없습니다.  
  
[sealed](../../windows/sealed-cpp-component-extensions.md) 로 표시된 클래스는 다른 클래스의 기본 클래스일 수 없습니다.  
  
다음 샘플에서는 C3246을 생성합니다.  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  
