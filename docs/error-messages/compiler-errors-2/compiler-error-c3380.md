---
title: "컴파일러 오류 C3380 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 11
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
ms.openlocfilehash: fbc75caa22d3c46b5a7a487662119a43b27eaf2b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3380"></a>컴파일러 오류 C3380
'class': 어셈블리 액세스 지정자가 잘못되었습니다. 'public' 또는 'private'만 사용할 수 있습니다.  
  
 관리 되는 클래스 또는 구조체에 적용 하는 경우는 [공용](../../cpp/public-cpp.md) 및 [개인](../../cpp/private-cpp.md) 키워드는 클래스 어셈블리 메타 데이터를 통해 노출 될 있는지 여부를 나타냅니다. 만 `public` 또는 `private` 으로 컴파일한 프로그램의 클래스에 적용할 수 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 `ref` 및 `value` 키워드를 함께 사용 하면 [/clr](../../build/reference/clr-common-language-runtime-compilation.md), 관리 되는 클래스를 나타냅니다 (참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
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

