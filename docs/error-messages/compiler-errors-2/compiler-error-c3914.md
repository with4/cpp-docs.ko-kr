---
title: "컴파일러 오류 C3914 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3914
dev_langs:
- C++
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: fd21be63cc46f6108bd84615e9dbeccbcb39b1cc
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3914"></a>컴파일러 오류 C3914
기본 속성은 정적일 수 없습니다.  
  
기본 속성을 올바르게 선언 되었습니다.  자세한 내용은 참조 [하는 방법: 사용 하 여 속성에 C + + CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3914 오류가 발생 하 고 해결 하는 방법을 보여 줍니다.  
  
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
