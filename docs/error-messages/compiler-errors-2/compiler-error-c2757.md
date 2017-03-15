---
title: "컴파일러 오류 C2757 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2757
dev_langs:
- C++
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
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
ms.openlocfilehash: 993b67c619cd56e4245b0195e1f8446577b7ecc8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2757"></a>컴파일러 오류 C2757
'symbol':이 이름 가진 기호가 이미를이 이름은 네임 스페이스 이름으로 사용할 수 없습니다  
  
 네임 스페이스 식별자로 현재 컴파일에 사용 되는 기호 참조 된 어셈블리에서 이미 사용 중입니다.  
  
 다음 샘플에서는 C2757 오류가 생성 됩니다.  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 그리고  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  

