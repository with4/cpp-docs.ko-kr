---
title: 컴파일러 오류 C3807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3807
dev_langs:
- C++
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4171b13d7605d296ac8ac6d1f06125d0fadd226
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272320"
---
# <a name="compiler-error-c3807"></a>컴파일러 오류 C3807
'type': ComImport 특성이 있는 클래스 'type2'에서 파생 될 수 없습니다, 인터페이스 구현에만 사용할 수 있습니다.  
  
 파생 된 형식은 <xref:System.Runtime.InteropServices.ComImportAttribute> 만 인터페이스를 구현할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3807 오류가 발생 합니다.  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```