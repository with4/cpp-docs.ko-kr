---
title: 컴파일러 오류 C3838 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3838
dev_langs:
- C++
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dea27fde00773ccdaf7acb2dff135cd3cf894da4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3838"></a>컴파일러 오류 C3838
명시적으로 'type'에서 상속할 수 없습니다.  
  
 지정 된 `type` 클래스에서 기본 클래스로 사용할 수 없습니다.  
  
## <a name="example"></a>예제
 다음 샘플에서는 C3838 오류가 생성 됩니다.  
  
```  
// C3838a.cpp  
// compile with: /clr /c  
public ref class B : public System::Enum {};   // C3838  
```  
