---
title: 컴파일러 경고 C4687 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad45c4bb2456b3bc23114233c084bbad1551e27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272723"
---
# <a name="compiler-warning-c4687"></a>컴파일러 경고 C4687
'class': 봉인된 추상 클래스는 ' interface '인터페이스를 구현할 수 없습니다  
  
 봉인 된 추상 형식은 일반적으로 정적 멤버 함수를 유지 하는 데만 합니다.  
  
 자세한 내용은 참조 [추상](../../windows/abstract-cpp-component-extensions.md)및 [봉인](../../windows/sealed-cpp-component-extensions.md)합니다.  
  
 기본적으로 오류로 C4687 발급 됩니다. C4687 표시 하지 않을 수 있습니다는 [경고](../../preprocessor/warning.md) pragma입니다. 인 경우 sealed로 표시 된 추상 형식에는 인터페이스를 구현 하려면 C4687 억제할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4687 오류가 발생 합니다.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```