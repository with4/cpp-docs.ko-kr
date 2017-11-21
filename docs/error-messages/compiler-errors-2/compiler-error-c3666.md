---
title: "컴파일러 오류 C3666 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3666
dev_langs: C++
helpviewer_keywords: C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0bd78e2d14805ab84f1d32300f1cf95a1daf91d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3666"></a>컴파일러 오류 C3666
'constructor': 재정의 지정자는 'keyword' 생성자에 사용할 수 없습니다  
  
 재정의 지정자는 생성자에서 사용 되었지만 및 허용 되지 않습니다. 자세한 내용은 참조 [재정의 지정자](../../windows/override-specifiers-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3666 오류가 발생 합니다.  
  
```  
// C3666.cpp  
// compile with: /clr /c  
ref struct R {  
   R() new {}   // C3666  
   R(int i) {}   // OK  
};  
```