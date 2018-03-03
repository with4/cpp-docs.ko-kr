---
title: "심각한 오류 C1308 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1308
dev_langs:
- C++
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4be04f3891e39c37924743ae86e2c7f62f92b6d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1308"></a>심각한 오류 C1308
링크 어셈블리는 지원 되지 않습니다.  
  
 .netmodule을 링커에 대한 입력 파일로 사용할 수 있지만 어셈블리는 사용할 수 없습니다. 로 컴파일된 어셈블리를 연결 하려고 시도 하는 경우이 오류가 발생할 `/clr:safe`합니다.  
  
 자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)을 참조하세요.  
  
 다음 샘플에서는 C1308 오류가 생성 됩니다.  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 그런 다음  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```