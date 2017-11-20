---
title: "컴파일러 오류 C3807 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3807
dev_langs: C++
helpviewer_keywords: C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc8e760d295cc0a4c2482449038ea09e89547425
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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