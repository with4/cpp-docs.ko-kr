---
title: "컴파일러 오류 C2844 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
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
ms.openlocfilehash: c6bfb80408e058d22977ff068c9a0c21d5353a90
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2844"></a>컴파일러 오류 C2844
'member': '인터페이스' 인터페이스의 멤버가 될 수 없습니다  
  
 [인터페이스 클래스](../../windows/interface-class-cpp-component-extensions.md) 경우가 아니라면 또한 속성 데이터 멤버를 포함할 수 없습니다.  
  
 속성 또는 멤버 함수 이외의 항목 인터페이스에는 허용 되지 않습니다. 또한 생성자, 소멸자 및 연산자 허용 되지 않습니다.  
  
 다음 샘플에서는 C2844 오류가 생성 됩니다.  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  

