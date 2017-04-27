---
title: "컴파일러 오류 C2492 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
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
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 54a650e967acb2ee0b6864780823111b4db9414c
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2492"></a>컴파일러 오류 C2492
'*변수*': 스레드 저장 기간이 있는 데이터에는 dll 인터페이스를 사용할 수 없습니다    
  
 으로 선언 된 변수는 [스레드](../../cpp/thread.md) 특성 및 DLL과 인터페이스입니다. 주소는 `thread` 변수 알 런타임까지 수 있으므로 한 DLL 가져오기 또는 내보내기에 연결할 수 없습니다.  
  
 다음 샘플에서는 C2492 오류가 생성 됩니다.  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```
