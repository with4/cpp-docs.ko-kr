---
title: "컴파일러 오류 C3179 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3179
dev_langs:
- C++
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 7175968669ff05ac61e1a60716d4cd04941d37ba
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3179"></a>컴파일러 오류 C3179
명명되지 않은 관리되는 형식 또는 WinRT 형식을 사용할 수 없습니다.  
  
모든 CLR 및 WinRT 클래스와 구조체에는 이름이 있어야 합니다.  
  
다음 샘플에서는 C3179 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  

