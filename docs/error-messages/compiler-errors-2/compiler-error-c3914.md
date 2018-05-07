---
title: 컴파일러 오류 C3914 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3914
dev_langs:
- C++
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3818c54f3720bdff92280e04a4750ed1b4f238c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3914"></a>컴파일러 오류 C3914
기본 속성은 정적일 수 없습니다.  
  
기본 속성이 잘못 선언 되었습니다.  자세한 내용은 참조 [하는 방법: 사용 하 여 속성 C + + /cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3914 오류가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```  
// C3914.cpp  
// compile with: /clr /c  
ref struct X {  
   static property int default[int] {   // C3914  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```