---
title: "컴파일러 오류 C3380 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8789889ab0d9ebe93941a438c286ed718ac4721
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3380"></a>컴파일러 오류 C3380
'class': 어셈블리 액세스 지정자가 잘못되었습니다. 'public' 또는 'private'만 사용할 수 있습니다.  
  
 관리되는 클래스 또는 구조체에 적용하는 경우 [public](../../cpp/public-cpp.md) 및 [private](../../cpp/private-cpp.md) 키워드는 클래스가 어셈블리 메타데이터를 통해 노출되는지 여부를 나타냅니다. `public` 또는 `private` 만 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)로 컴파일된 프로그램의 클래스에 적용할 수 있습니다.  
  
 `ref` 및 `value` 키워드와 함께 사용할 경우 [/clr](../../build/reference/clr-common-language-runtime-compilation.md), 관리 되는 클래스를 나타냅니다 (참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 다음 샘플에서는 C3380을 생성합니다.  
  
```  
// C3380_2.cpp  
// compile with: /clr  
protected ref class A {   // C3380  
// try the following line instead  
// ref class A {  
public:  
   static int i = 9;  
};  
  
int main() {  
   A^ myA = gcnew A;  
   System::Console::WriteLine(myA->i);  
}  
```  
