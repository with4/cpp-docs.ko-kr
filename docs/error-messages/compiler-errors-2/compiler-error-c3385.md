---
title: "컴파일러 오류 C3385 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3385
dev_langs:
- C++
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 88eb849cff4eb32db7f7355b276eaefbc7a49ffd
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3385"></a>컴파일러 오류 C3385
'class::function': DllImport 사용자 지정 특성을 가진 함수는 클래스의 인스턴스를 반환할 수 없습니다.  
  
 `DllImport` 특성으로 지정된 .dll 파일에 있는 것으로 정의된 함수는 클래스의 인스턴스를 반환할 수 없습니다.  
  
 다음 샘플에서는 C3385를 생성합니다.  
  
```  
// C3385.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
struct SomeStruct1 {};  
  
public ref struct Wrap {  
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]  
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385  
};  
```  

