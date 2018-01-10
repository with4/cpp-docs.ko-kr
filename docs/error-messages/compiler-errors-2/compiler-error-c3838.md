---
title: "컴파일러 오류 C3838 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3838
dev_langs: C++
helpviewer_keywords: C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6204502c03e7428194059ae2e49ffa8f9fa95481
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3838"></a>컴파일러 오류 C3838
명시적으로 'type'에서 상속할 수 없습니다.  
  
 지정 된 `type` 클래스에서 기본 클래스로 사용할 수 없습니다.  
  
## <a name="example"></a>예
 다음 샘플에서는 C3838 오류가 생성 됩니다.  
  
```  
// C3838a.cpp  
// compile with: /clr /c  
public ref class B : public System::Enum {};   // C3838  
```  
