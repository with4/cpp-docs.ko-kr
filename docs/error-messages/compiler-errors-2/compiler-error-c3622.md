---
title: "컴파일러 오류 C3622 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ed81cc21e3c3ae574a0c83a692f75638d24111de
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3622"></a>컴파일러 오류 C3622
'class': '키워드'를 인스턴스화할 수 없는 클래스 선언  
  
로 표시 된 클래스를 인스턴스화하고 하려고 [추상](../../windows/abstract-cpp-component-extensions.md)합니다. 로 표시 되어 있는 클래스 `abstract` 기본 클래스인 수 있지만 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3622 오류가 발생 합니다.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  

