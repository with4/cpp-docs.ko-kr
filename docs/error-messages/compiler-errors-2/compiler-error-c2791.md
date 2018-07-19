---
title: 컴파일러 오류 C2791 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2791
dev_langs:
- C++
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65a3d399ed6c7f25b849335328550526ecf7a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236498"
---
# <a name="compiler-error-c2791"></a>컴파일러 오류 C2791
'super'를 잘못 사용 했습니다: 'class' 기본 클래스가 없습니다  
  
 키워드 [super](../../cpp/super.md) 의 기본 클래스를 사용 하지 않는 클래스 멤버 함수의 컨텍스트 내에서 사용 되었습니다.  
  
 다음 샘플에서는 C2791 오류가 생성 됩니다.  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```