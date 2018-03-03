---
title: "컴파일러 오류 C2521 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2521
dev_langs:
- C++
helpviewer_keywords:
- C2521
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f592e17dab18decfa73652a6a3a6d459fbd62ee4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2521"></a>컴파일러 오류 C2521
함수는 인수를 사용 하지 않습니다.  
  
 인수는 소멸자 또는 종료자를 사용 하려고 했습니다.  
  
 자세한 내용은 참조 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2521 오류가 발생 합니다.  
  
```  
// C2521.cpp  
// compile with: /clr  
ref class R {  
protected:  
   !R() {}  
  
public:  
   void CleanUp() {  
      this->!R(4);   // C2521  
      this->!R();   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R();  
   r->CleanUp();  
}  
```