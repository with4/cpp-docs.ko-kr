---
title: "컴파일러 오류 C3246 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b55a604a45aa7b8dc37659ca3a4f9affa4106d21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
