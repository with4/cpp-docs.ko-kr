---
title: 컴파일러 오류 C3799 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3799
dev_langs:
- C++
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5e13e1e92b3f821ffbed62b06bd601baac7aad9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267305"
---
# <a name="compiler-error-c3799"></a>컴파일러 오류 C3799
인덱싱된 속성에는 빈 매개 변수 목록을 사용할 수 없습니다.  
  
인덱싱된 속성을 잘못 선언 되었습니다. 자세한 내용은 참조 [하는 방법: 사용 하 여 속성 C + + /cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3799 오류가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```cpp  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```