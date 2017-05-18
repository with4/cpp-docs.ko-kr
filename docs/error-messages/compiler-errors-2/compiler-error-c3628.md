---
title: "컴파일러 오류 C3628 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: e8723f85289d1094a6969d2bf26c30a85ccf382b
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3628"></a>컴파일러 오류 C3628
'기본 클래스': 관리 또는 WinRTclasses는 공용 상속만 지원  
  
관리 되는 또는 WinRT 사용 하려고 했습니다으로 클래스는 [개인](../../cpp/private-cpp.md) 또는 [보호](../../cpp/protected-cpp.md) 기본 클래스입니다. 관리 되는 또는 WinRT 클래스를 기본 클래스로 사용할 수 있습니다 [공용](../../cpp/public-cpp.md) 액세스 합니다.  
  
다음 샘플에서는 C3628을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  

